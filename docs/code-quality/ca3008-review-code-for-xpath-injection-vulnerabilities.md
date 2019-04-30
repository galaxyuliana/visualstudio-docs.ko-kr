---
title: 'CA3008: 코드에서 XPath 삽입 취약성에 대해 검토합니다.'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e66b75160df0e8ecf9d33601ee383ec71cd62c4d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806481"
---
# <a name="ca3008-review-code-for-xpath-injection-vulnerabilities"></a>CA3008: 코드에서 XPath 삽입 취약성에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForXPathInjectionVulnerabilities|
|CheckId|CA3008|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 XPath 쿼리에 도달합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력에서 작업할 때 XPath 주입 공격에 주의 해야 합니다. 신뢰할 수 없는 입력을 사용 하 여 XPath 쿼리를 구성할 공격자가 악의적 의도 하지 않은 결과 반환 하도록 쿼리를 조작 하 고 가능한 쿼리 XML의 콘텐츠를 공개할 수 있습니다. 

이 규칙은 입력 XPath 식에 도달 하는 HTTP 요청을 찾으려고 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 XPath 쿼리를 수행 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

XPath 주입 취약점을 해결 방법 몇 가지는 다음과 같습니다.

- 사용자 입력에서 XPath 쿼리를 생성 하지 마십시오.
- 입력 문자 집합을 안전 하 게만 포함 되어 있는지 확인 합니다.
- 따옴표를 이스케이프 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

안전에 대 한 입력을 확인 했으면를 알고 있으면이 경고를 표시 하지 않아도 괜찮습니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.Xml.XPath;

public partial class WebForm : System.Web.UI.Page
{
    public XPathNavigator AuthorizedOperations { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string operation = Request.Form["operation"];

        // If an attacker uses this for input:
        //     ' or 'a' = 'a
        // Then the XPath query will be:
        //     authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        // and it will return any authorizedOperation node.
        XPathNavigator node = AuthorizedOperations.SelectSingleNode(
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']");
    }
}
```

```vb
Imports System
Imports System.Xml.XPath

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Public Property AuthorizedOperations As XPathNavigator

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim operation As String = Me.Request.Form("operation")
        
        ' If an attacker uses this for input:
        '     ' or 'a' = 'a
        ' Then the XPath query will be:
        '      authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        ' and it will return any authorizedOperation node.
        Dim node As XPathNavigator = AuthorizedOperations.SelectSingleNode( _
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']")
    End Sub
End Class
```
