---
title: 'CA3075: DTD 처리가 안전하지 않습니다.'
ms.date: 03/18/2019
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6de817e3aaecbdd1c89cc2174e91126ea39d99d7
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194621"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: DTD 처리가 안전하지 않습니다.

|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

안전하지 않은 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 인스턴스를 사용하거나 외부 엔터티 소스를 참조하면 파서는 신뢰할 수 없는 입력을 허용하고 공격자에게 중요 한 정보를 공개할 수 있습니다.

## <a name="rule-description"></a>규칙 설명

*DTD(문서 종류 정의)* 는 XML 파서가  [W3C(World Wide Web Consortium) XML(Extensible Markup Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)에 정의된 대로 문서의 유효성을 확인할 수 있는 두 가지 방법 중 하나입니다. 이 규칙은 속성 및 개발자 가능성에 대 한 경고를 신뢰할 수 없는 데이터가 허용 되는 인스턴스에 찾아 [정보 공개](/dotnet/framework/wcf/feature-details/information-disclosure) 위협 또는 [서비스 거부 (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) 공격입니다. 다음 경우에 이 규칙이 트리거됩니다.

- <xref:System.Xml.XmlReader> 를 사용하여 외부 XML 엔터티를 확인하는 <xref:System.Xml.XmlUrlResolver>인스턴스에서 DtdProcessing이 사용되도록 설정된 경우

- XML의 <xref:System.Xml.XmlNode.InnerXml%2A> 속성이 설정된 경우

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 속성이는 Parse로 설정 됩니다.

- 입력 처리를 사용 하 여 신뢰할 수 없는 <xref:System.Xml.XmlResolver> 대신 <xref:System.Xml.XmlSecureResolver>합니다.

- 합니다 <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> 메서드가 호출 됩니다는 안전 하지 않은 <xref:System.Xml.XmlReaderSettings> 인스턴스 또는 인스턴스 없이 합니다.

- <xref:System.Xml.XmlReader> 안전 하지 않은 기본 설정이 나 값을 사용 하 여 생성 됩니다.

이러한 경우에는 모든 결과 동일 합니다: 콘텐츠 중 하나는 파일 시스템 또는 네트워크 공유에서 XML 처리 되는 컴퓨터에서 공격자에 게 노출 될 또는 DoS 벡터로 DTD 처리를 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- Catch 하 고 적절 하 게 경로 정보가 공개 되지 않도록 모든 XmlTextReader 예외를 처리 합니다.

- 사용 하 여는 <xref:System.Xml.XmlSecureResolver> XmlTextReader에서 액세스할 수 있는 리소스를 제한 합니다.

- <xref:System.Xml.XmlReader> 속성을 <xref:System.Xml.XmlResolver> null **로 설정하여**가 외부 리소스를 열 수 없도록 합니다.

- 확인을 <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A?displayProperty=nameWithType> 속성이 신뢰할 수 있는 소스에서 할당 됩니다.

**.NET 3.5 및 이전 버전**

- 신뢰할 수 없는 소스를 설정 하 여 처리 하는 경우 DTD 처리를 사용 하지 않도록 설정 합니다 <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> 속성을 **true**합니다.

- XmlTextReader 클래스에는 완전 신뢰 상속 요청이 있습니다.

**.NET 4 이상**

- 설정 하 여 신뢰할 수 없는 소스를 처리 하는 경우 DtdProcessing을 설정 하지 않도록 합니다 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> 속성을 **금지** 또는 **무시**합니다.

- Load() 메서드가 모든 InnerXml 경우에서 XmlReader 인스턴스를 사용하는지 확인합니다.

> [!NOTE]
> 이 규칙은 일부 유효한 XmlSecureResolver 인스턴스에 대해 가양성(false positive)을 보고할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlReader reader = XmlReader.Create(sreader, new XmlReaderSettings() { XmlResolver = null });
    doc.Load(reader);
}
```

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlReader reader = XmlReader.Create(stream, new XmlReaderSettings() { XmlResolver = null });
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlReader reader = XmlReader.Create(path, new XmlReaderSettings() { XmlResolver = null });
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings() { XmlResolver = null };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```
