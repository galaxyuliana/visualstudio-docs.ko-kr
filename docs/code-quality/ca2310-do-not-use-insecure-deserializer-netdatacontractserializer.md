---
title: 'CA2310: 안전하지 않은 역직렬 변환기 NetDataContractSerializer를 사용하지 마세요.'
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
ms.openlocfilehash: 09496fd11945ec4d419cc215569a7436f96d71ec
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891145"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310: 안전하지 않은 역직렬 변환기 NetDataContractSerializer를 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

Deserialization <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> 메서드를 호출 했거나 참조 했습니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙은 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> deserialization 메서드 호출 또는 참조를 찾습니다. <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성이 유형 제한으로 설정 된 경우에만 deserialize 하려면이 규칙을 사용 하지 않도록 설정 하 고 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 및 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) 규칙을 대신 사용 하도록 설정 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능 하면 보안 serializer를 대신 사용 하 고 **공격자가 deserialize 할 임의의 형식을 지정할 수 없도록**합니다. 몇 가지 안전한 serializer는 다음과 같습니다.
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType>-사용 <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>하지 마세요. 형식 확인자를 사용 해야 하는 경우 deserialize 된 형식을 예상 목록으로 제한 합니다.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft.json Json.NET-TypeNameHandling를 사용 합니다. TypeNameHandling에 다른 값을 사용 해야 하는 경우 사용자 지정 ISerializationBinder를 사용 하 여 deserialize 된 형식을 예상 목록으로 제한 합니다.
  - 프로토콜 버퍼
- Serialize 된 데이터를 변조 방지로 설정 합니다. Serialization 후 직렬화 된 데이터를 암호화 하 여 서명 합니다. Deserialization 전에 암호화 서명 유효성을 검사 합니다. 암호화 키가 공개 되지 않도록 보호 하 고 키 회전을 설계 합니다.
- Deserialize 된 형식을 제한 합니다. 사용자 지정 <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>를 구현 합니다. 로 <xref:System.Runtime.Serialization.NetDataContractSerializer>deserialize 하기 전에 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성을 사용자 지정 <xref:System.Runtime.Serialization.SerializationBinder>의 인스턴스로 설정 합니다. 재정의 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> 된 메서드에서 형식이 예기치 않은 경우 예외를 throw 하 여 deserialization을 중지 합니다.
  - Deserialize 된 형식을 제한 하는 경우이 규칙을 사용 하지 않도록 설정 하 고 [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 및 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)규칙을 사용 하도록 설정 하는 것이 좋습니다. [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) 및 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) 규칙은 deserialize 전에 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성이 항상 설정 되도록 하는 데 도움이 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 코드 예제

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

## <a name="related-rules"></a>관련 규칙

[CA2311: 먼저 NetDataContractSerializer를 설정 하지 않고 deserialize 하지 마십시오.](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312: Deserialize 전에 NetDataContractSerializer이 설정 되었는지 확인 합니다.](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
