---
title: 'CA3002: 코드에서 XSS 취약점에 대해 검토합니다.'
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
ms.openlocfilehash: a10f72297746a1e7bda3c69f8f7daf0efacd20bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541270"
---
# <a name="ca3002-review-code-for-xss-vulnerabilities"></a>CA3002: 코드에서 XSS 취약점에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForXssVulnerabilities|
|CheckId|CA3002|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 원시 HTML 출력에 도달합니다.

## <a name="rule-description"></a>규칙 설명

웹 요청에서 신뢰할 수 없는 입력을 사용 하는 경우 사이트 간 스크립팅 (XSS) 공격에 주의 해야 합니다. XSS 공격이 공격자가 악성 스크립트를 실행 하거나 악의적으로 웹 페이지의 콘텐츠를 수정할 수 있도록 원시 HTML 출력에 신뢰할 수 없는 입력을 삽입 합니다. 배치 하는 일반적인 기술 `<script>` 입력에 악성 코드를 사용 하 여 요소입니다. 자세한 내용은 [OWASP의 XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS))합니다.

이 규칙은 입력 원시 HTML 출력에 도달 하는 HTTP 요청을 찾으려고 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 원시 HTML을 출력 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 원시 HTML 출력을 대신 사용 하 여 메서드 또는 속성을 해당 첫 번째 HTML로 인코딩하여 해당 입력 합니다.
- 원시 HTML을 출력 하기 전에 HTML 인코딩해야 신뢰할 수 없는 데이터입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.
- 입력의 유효성을 검사 알려진된 안전한 HTML을 포함 하지 않는 문자 집합이 있는지 알 수 있습니다.
- 이 규칙에 의해 검색 되지 방식으로 HTML로 인코딩된 데이터가 알 수 있습니다.

> [!NOTE]
> 이 규칙 보고할 수 있습니다 거짓 긍정 일부 메서드 또는 속성에 대 한 해당 HTML 인코딩할 입력 합니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Response.Write("<HTML>" + input + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")
        Me.Response.Write("<HTML>" + input + "</HTML>")
    End Sub
End Class
```

### <a name="solution"></a>솔루션

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];

        // Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Response.Write("<HTML>" + Server.HtmlEncode(input) + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")

        ' Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Me.Response.Write("<HTML>" + Me.Server.HtmlEncode(input) + "</HTML>")
    End Sub
End Class
```