---
title: 'CA3077: API 디자인, XML 문서 및 XML 텍스트 판독기의 처리가 안전하지 않습니다.'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ca39cef1fb4f1bf1114673dd96a91a1ac8e105cc
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919870"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: API 디자인, XML 문서 및 XML 텍스트 판독기의 처리가 안전하지 않습니다.

|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
XMLDocument 및 XMLTextReader에서 파생된 API를 디자인할 경우 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>에 주의해야 합니다.  외부 엔터티 소스를 참조하거나 확인할 때 안전하지 않은 DTDProcessing 인스턴스를 사용하거나 XML에서 안전하지 않은 값을 설정하면 정보가 공개될 수 있습니다.

## <a name="rule-description"></a>규칙 설명
*DTD(문서 종류 정의)* 는 XML 파서가  [W3C(World Wide Web Consortium) XML(Extensible Markup Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)에 정의된 대로 문서의 유효성을 확인할 수 있는 두 가지 방법 중 하나입니다. 이 규칙은 신뢰할 수 없는 데이터가 허용되는 속성 및 인스턴스를 찾아 [DoS(서비스 거부)](/dotnet/framework/wcf/feature-details/information-disclosure) 공격을 야기할 수 있는 잠재적인 [Information Disclosure](/dotnet/framework/wcf/feature-details/denial-of-service) 위협을 개발자에게 경고합니다. 다음 경우에 이 규칙이 트리거됩니다.

- <xref:System.Xml.XmlDocument>또는 <xref:System.Xml.XmlTextReader> 클래스는 DTD 처리에 기본 해결 프로그램 값을 사용 합니다.

- XmlDocument 또는 XmlTextReader 파생 클래스에 대해 정의된 생성자가 없거나 <xref:System.Xml.XmlResolver>에 대해 보안 값이 사용되지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 모든 XmlTextReader 예외를 Catch 하 고 처리 하 여 경로 정보가 공개 되지 않도록 합니다.

- XmlResolver <xref:System.Xml.XmlSecureResolver>대신를 사용 하 여 XmlTextReader가 액세스할 수 있는 리소스를 제한 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass () {} // warn
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2() // warn
        {
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass ()
        {
            XmlResolver = null;
        }
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2()
        {
               XmlResolver = null;
        }
    }
}
```