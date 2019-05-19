---
title: 'CA3007: 코드에서 오픈 리디렉션 취약점에 대해 검토합니다.'
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
ms.openlocfilehash: e60d0fad1262138b57f079485bc7455e55c7ec25
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841338"
---
# <a name="ca3007-review-code-for-open-redirect-vulnerabilities"></a>CA3007: 코드에서 오픈 리디렉션 취약점에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForOpenRedirectVulnerabilities|
|CheckId|CA3007|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 HTTP 응답 리디렉션을 도달합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력을 사용 하는 경우 오픈 리디렉션 취약성에 주의 해야 합니다. 공격자는 합법적인 URL의 모양을 제공 하지만 리디렉션하는 모르는 방문자는 피싱 또는 다른 악성 웹 페이지에 웹 사이트를 사용 하는 오픈 리디렉션 취약점을 악용할 수 있습니다.

이 규칙은 입력 HTTP 리디렉션 URL에 도달 하는 HTTP 요청을 찾으려고 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 HTTP 리디렉션을 사용 하 여 응답 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [분석기 구성](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) EditorConfig 파일에 제한을 구성 하는 방법에 대 한 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

오픈 리디렉션 취약점으로 인 한 해결 방법 몇 가지는 다음과 같습니다.

- 리디렉션을 시작할 수 없습니다.
- 리디렉션 시나리오에서 URL의 일부를 지정 하는 사용자를 허용 하지 마십시오.
- 미리 정의 된 "허용"으로 목록 url 리디렉션을 제한 합니다.
- 유효성 검사 리디렉션 Url입니다.
- 해당 하는 경우에 사이트에서 사용자가 리디렉션되는 경우 고 지 사항 페이지를 사용 하는 것이 좋습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

원하는 Url로 제한할 수에 대 한 입력을 확인 했으면를 알고 있으면이 경고를 표시 하지 않아도 괜찮습니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["url"];
        this.Response.Redirect(input);
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("url")
        Me.Response.Redirect(input)
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
        if (String.IsNullOrWhiteSpace(input))
        {
            this.Response.Redirect("https://example.org/login.html");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("in")
        If String.IsNullOrWhiteSpace(input) Then
            Me.Response.Redirect("https://example.org/login.html")
        End If
    End Sub
End Class
```
