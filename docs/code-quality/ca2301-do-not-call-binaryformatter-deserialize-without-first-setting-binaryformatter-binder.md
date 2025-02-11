---
title: 'CA2301: 먼저 BinaryFormatter.Binder를 설정하지 않고 BinaryFormatter.Deserialize를 호출하지 마세요.'
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
f1_keywords:
- CA2301
- DoNotCallBinaryFormatterDeserializeWithoutFirstSettingBinaryFormatterBinder
ms.openlocfilehash: 0291aa4d8130cfdc9b919e0c8430e56ef0f95296
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891188"
---
# <a name="ca2301-do-not-call-binaryformatterdeserialize-without-first-setting-binaryformatterbinder"></a>CA2301: 먼저 BinaryFormatter.Binder를 설정하지 않고 BinaryFormatter.Deserialize를 호출하지 마세요.

|||
|-|-|
|TypeName|DoNotCallBinaryFormatterDeserializeWithoutFirstSettingBinaryFormatterBinder|
|CheckId|CA2301|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 속성 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> 을 설정 하지 않고 deserialization 메서드를 호출 했거나 참조 했습니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 에<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 집합이 없는 경우 deserialization 메서드 호출 또는 참조를 찾습니다. <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 속성에 관계 없이를 사용 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 하 여 deserialization을 허용 하지 않으려면이 규칙 및 [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)를 사용 하지 않도록 설정 하 고 규칙 [CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)을 사용 하도록 설정 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능 하면 보안 serializer를 대신 사용 하 고 **공격자가 deserialize 할 임의의 형식을 지정할 수 없도록**합니다. 몇 가지 안전한 serializer는 다음과 같습니다.
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType>-사용 <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>하지 마세요. 형식 확인자를 사용 해야 하는 경우 deserialize 된 형식을 예상 목록으로 제한 합니다.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft.json Json.NET-TypeNameHandling를 사용 합니다. TypeNameHandling에 다른 값을 사용 해야 하는 경우 사용자 지정 ISerializationBinder를 사용 하 여 deserialize 된 형식을 예상 목록으로 제한 합니다.
  - 프로토콜 버퍼
- Serialize 된 데이터를 변조 방지로 설정 합니다. Serialization 후 직렬화 된 데이터를 암호화 하 여 서명 합니다. Deserialization 전에 암호화 서명 유효성을 검사 합니다. 암호화 키가 공개 되지 않도록 보호 하 고 키 회전을 설계 합니다.
- Deserialize 된 형식을 제한 합니다. 사용자 지정 <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>를 구현 합니다. 로 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>deserialize 하기 전에 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> 속성을 사용자 지정 <xref:System.Runtime.Serialization.SerializationBinder>의 인스턴스로 설정 합니다. 재정의 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> 된 메서드에서 형식이 예기치 않은 경우 예외를 throw 하 여 deserialization을 중지 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>해결 방법

```csharp
using System;
using System.IO;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;

public class BookRecordSerializationBinder : SerializationBinder
{
    public override Type BindToType(string assemblyName, string typeName)
    {
        // One way to discover expected types is through testing deserialization
        // of **valid** data and logging the types used.

        ////Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')");

        if (typeName == "BookRecord" || typeName == "AisleLocation")
        {
            return null;
        }
        else
        {
            throw new ArgumentException("Unexpected type", nameof(typeName));
        }
    }
}

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        formatter.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization
Imports System.Runtime.Serialization.Formatters.Binary

Public Class BookRecordSerializationBinder
    Inherits SerializationBinder

    Public Overrides Function BindToType(assemblyName As String, typeName As String) As Type
        ' One way to discover expected types is through testing deserialization
        ' of **valid** data and logging the types used.

        'Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')")

        If typeName = "BinaryFormatterVB.BookRecord" Or typeName = "BinaryFormatterVB.AisleLocation" Then
            Return Nothing
        Else
            Throw New ArgumentException("Unexpected type", NameOf(typeName))
        End If
    End Function
End Class

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        formatter.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>관련 규칙

[CA2300: 안전 하지 않은 역직렬 변환기 BinaryFormatter를 사용 하지 마십시오.](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)

[CA2302: BinaryFormatter를 설정 해야 합니다. BinaryFormatter를 호출 하기 전에 바인더를 설정 하십시오. Deserialize](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)