---
title: 'CA3012: 정규식 주입 취약점에 대 한 코드를 검토 합니다.'
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
ms.openlocfilehash: 114b44ec566554c81f5caf3b8ac474f9c5a75c07
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018588"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012: 정규식 주입 취약점에 대 한 코드를 검토 합니다.

|||
|-|-|
|TypeName|ReviewCodeForRegexInjectionVulnerabilities|
|CheckId|CA3012|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 정규식에 도달합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력에서 작업할 때 regex 삽입 공격에 주의 해야 합니다. 공격자가 regex 주입을 사용 하 여 악의적으로 정규식을 의도 하지 않은 결과 일치 하는 정규식을 확인 하거나 서비스 거부 공격이 발생 하는 과도 한 CPU를 사용 하는 regex를 수정 수 있습니다.

이 규칙 정규식에 도달 하는 HTTP 요청에서 입력을 찾으려고 시도 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 정규식을 만드는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

Regex 삽입에 대 한 일부 완화는 다음과 같습니다.

- 항상 사용 하는 [제한 시간을 일치](/dotnet/standard/base-types/best-practices#use-time-out-values) 정규식을 사용 하는 경우.
- 사용자 입력을 기반으로 하는 정규식을 사용 하지 마십시오.
- 호출 하 여 사용자 입력에서 특수 문자를 이스케이프 <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName> 나 다른 방법입니다.
- 사용자가 입력만 특수 하지 않은 문자를 허용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

사용 하는 것이 알고 있는 경우는 [제한 시간을 일치](/dotnet/standard/base-types/best-practices#use-time-out-values) 사용자는 특수 문자를이 경고를 표시 하지 않아도 괜찮습니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.Text.RegularExpressions;

public partial class WebForm : System.Web.UI.Page
{
    public string SearchableText { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string findTerm = Request.Form["findTerm"];
        Match m = Regex.Match(SearchableText, "^term=" + findTerm);
    }
}
```

```vb
Imports System
Imports System.Text.RegularExpressions

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Public Property SearchableText As String

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim findTerm As String = Request.Form("findTerm")
        Dim m As Match = Regex.Match(SearchableText, "^term=" + findTerm)
    End Sub
End Class
```
