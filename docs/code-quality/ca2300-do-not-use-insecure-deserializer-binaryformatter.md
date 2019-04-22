---
title: 'CA2300: 안전하지 않은 역직렬 변환기 BinaryFormatter를 사용하지 마세요.'
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2e3ad5c23d880c65a57fdd94739475537c1aebff
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59367301"
---
# <a name="ca2300-do-not-use-insecure-deserializer-binaryformatter"></a>CA2300: 안전하지 않은 역직렬 변환기 BinaryFormatter를 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerBinaryFormatter|
|CheckId|CA2300|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> deserialization 메서드를 호출 하거나 참조 합니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙을 찾습니다 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> 메서드 호출 또는 참조를 역직렬화 합니다. 경우에만 deserialize 하려는 경우는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 속성 형식을 제한 하 고,이 규칙을 사용 하지 않도록 설정 및 규칙을 사용 하도록 설정 [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) 하 고 [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) 대신 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능한 경우 보안 직렬 변환기를 대신 사용 하 고 **공격자가 임의의 형식을 deserialize 하는 데 지정 하지**합니다. 안전한 일부 serializer는 다음과 같습니다.
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -사용해 서는 안 <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>합니다. 형식 확인자를 사용 해야 하는 경우 예상 되는 목록에 deserialize 된 형식을 제한 해야 합니다.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET-TypeNameHandling.None를 사용 합니다. TypeNameHandling에 대 한 다른 값을 사용 해야 하는 경우 예상 되는 목록에 deserialize 된 형식 제한 해야 합니다.
  - 프로토콜 버퍼
- Serialize 된 데이터 변조를 확인 합니다. Serialization 한 후 serialize 된 데이터를 암호화 하 여 로그인 합니다. 를 역직렬화 하기 전에 암호화 서명을 확인 합니다. 노출 되는 암호화 키를 보호 해야 하 고 키 회전에 대 한 디자인 해야 합니다.
- Deserialize 된 형식을 제한 합니다. 사용자 지정 구현 <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>합니다. 로 역직렬화 하기 전에 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>로 설정 합니다 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 사용자의 인스턴스에 대 한 속성 <xref:System.Runtime.Serialization.SerializationBinder>합니다. 재정의 된 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> 메서드, 형식에 예기치 않은 경우 다음 예외를 throw 합니다.
 - 역직렬화 된 형식에 대 한 사용자 제한 수 하려는 경우이 규칙을 사용 하지 않도록 설정 하 고 규칙을 사용 하도록 설정 [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) 하 고 [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)합니다. 규칙을 사용 하도록 설정 [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) 하 고 [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) 있는지 확인 하는 데 도움이 됩니다는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 속성은 항상 역직렬화 하기 전에 설정 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

- 입력이 신뢰할 수 있는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 응용 프로그램의 신뢰 경계 및 데이터 흐름 시간이 지남에 따라 변경 될 수 있다는 것이 좋습니다.
- 위의 주의 사항 중 하나를 수행한 경우이 경고를 표시 하지 않아도 안전 합니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>관련된 규칙

[CA2301: 첫 번째 설정은 BinaryFormatter.Binder 없이 BinaryFormatter.Deserialize를 호출 하지 마세요](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)

[CA2302: BinaryFormatter.Binder BinaryFormatter.Deserialize를 호출 하기 전에 설정 되어 있는지 확인](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)