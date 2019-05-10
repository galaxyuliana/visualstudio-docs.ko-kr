---
title: 'CA2311: 첫 번째 설정 NetDataContractSerializer.Binder 하지 않고 deserialize 하지 않습니다'
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
- CA2311
- DoNotDeserializeWithoutFirstSettingNetDataContractSerializerBinder
ms.openlocfilehash: aec95d4bbd2d9bc498f9688c5601591d480d7f3b
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135441"
---
# <a name="ca2311-do-not-deserialize-without-first-setting-netdatacontractserializerbinder"></a>CA2311: 첫 번째 설정 NetDataContractSerializer.Binder 하지 않고 deserialize 하지 않습니다

|||
|-|-|
|TypeName|DoNotDeserializeWithoutFirstSettingNetDataContractSerializerBinder|
|CheckId|CA2311|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

A <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> deserialization 메서드를 호출 하거나 하지 않고 참조 된 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성 집합입니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙을 찾습니다 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> 메서드 호출 또는 참조 deserialization 때 <xref:System.Runtime.Serialization.NetDataContractSerializer> 없는 해당 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 설정 합니다. 사용 하 여 모든 deserialization을 허용 하지 않도록 하려는 경우 <xref:System.Runtime.Serialization.NetDataContractSerializer> 에 관계 없이 합니다 <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> 속성을이 규칙을 사용 하지 않도록 설정 및 [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md), 규칙을 사용 하도록 설정 하 고 [CA2310](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md)합니다.

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

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.IO;
using System.Runtime.Serialization;

[DataContract]
public class BookRecord
{
    [DataMember]
    public string Title { get; set; }

    [DataMember]
    public string Author { get; set; }

    [DataMember]
    public int PageCount { get; set; }

    [DataMember]
    public AisleLocation Location { get; set; }
}

[DataContract]
public class AisleLocation
{
    [DataMember]
    public char Aisle { get; set; }

    [DataMember]
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) serializer.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization

<DataContract()>
Public Class BookRecord
    <DataMember()>
    Public Property Title As String

    <DataMember()>
    Public Property Author As String

    <DataMember()>
    Public Property Location As AisleLocation
End Class

<DataContract()>
Public Class AisleLocation
    <DataMember()>
    Public Property Aisle As Char

    <DataMember()>
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(serializer.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>솔루션

```csharp
using System;
using System.IO;
using System.Runtime.Serialization;

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

[DataContract]
public class BookRecord
{
    [DataMember]
    public string Title { get; set; }

    [DataMember]
    public string Author { get; set; }

    [DataMember]
    public int PageCount { get; set; }

    [DataMember]
    public AisleLocation Location { get; set; }
}

[DataContract]
public class AisleLocation
{
    [DataMember]
    public char Aisle { get; set; }

    [DataMember]
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        serializer.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) serializer.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization

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

<DataContract()>
Public Class BookRecord
    <DataMember()>
    Public Property Title As String

    <DataMember()>
    Public Property Author As String

    <DataMember()>
    Public Property Location As AisleLocation
End Class

<DataContract()>
Public Class AisleLocation
    <DataMember()>
    Public Property Aisle As Char

    <DataMember()>
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        serializer.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(serializer.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>관련된 규칙

[CA2310: 안전 하지 않은 역직렬 변환기가 NetDataContractSerializer 사용 하지 마세요](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md)

[CA2312: NetDataContractSerializer.Binder 역직렬화 하기 전에 설정 되어 있는지 확인](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)