---
title: 'CA2310: 안전 하지 않은 역직렬 변환기가 NetDataContractSerializer 사용 하지 마세요'
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2310
- DoNotUseInsecureDeserializerNetDataContractSerializer
ms.openlocfilehash: e4af6bbfbd7e14b99f39ffa0adb5d1117c200d9a
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135431"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310: 안전 하지 않은 역직렬 변환기가 NetDataContractSerializer 사용 하지 마세요

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> deserialization 메서드를 호출 하거나 참조 합니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙을 찾습니다 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> 메서드 호출 또는 참조를 역직렬화 합니다. 경우에만 deserialize 하려는 경우는 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성 형식을 제한 하 고,이 규칙을 사용 하지 않도록 설정 및 규칙을 사용 하도록 설정 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 하 고 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) 대신 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능한 경우 보안 직렬 변환기를 대신 사용 하 고 **공격자가 임의의 형식을 deserialize 하는 데 지정 하지**합니다. 안전한 일부 serializer는 다음과 같습니다.
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -사용해 서는 안 <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>합니다. 형식 확인자를 사용 해야 하는 경우 예상 되는 목록에 deserialize 된 형식을 제한 합니다.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET-TypeNameHandling.None를 사용 합니다. TypeNameHandling에 대 한 다른 값을 사용 해야 하는 경우 사용자 지정 ISerializationBinder 사용 하 여 예상된 목록에 deserialize 된 형식을 제한 합니다.
  - 프로토콜 버퍼
- Serialize 된 데이터 변조 증명을 확인 합니다. Serialization 한 후 serialize 된 데이터를 암호화 하 여 로그인 합니다. Deserialization을 수행 하기 전에 암호화 서명을 확인 합니다. 노출 되는 암호화 키 및 키 회전에 대 한 디자인을 보호 합니다.
- Deserialize 된 형식을 제한 합니다. 사용자 지정 구현 <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>합니다. 로 역직렬화 하기 전에 <xref:System.Runtime.Serialization.NetDataContractSerializer>로 설정 합니다 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 사용자의 인스턴스에 대 한 속성 <xref:System.Runtime.Serialization.SerializationBinder>합니다. 재정의 된 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> 메서드, 형식, 기대 없는 경우 예외를 throw 합니다.
- 역직렬화 된 형식에 대 한 사용자 제한 수 하려는 경우이 규칙을 사용 하지 않도록 설정 하 고 규칙을 사용 하도록 설정 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 하 고 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)합니다. 규칙 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 및 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) 하도록 도움말을 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성은 항상 역직렬화 하기 전에 설정 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Runtime.Serialization;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        return serializer.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        Return serializer.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>관련된 규칙

[CA2311: 첫 번째 설정 NetDataContractSerializer.Binder 하지 않고 deserialize 하지 않습니다](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312: NetDataContractSerializer.Binder 역직렬화 하기 전에 설정 되어 있는지 확인](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
