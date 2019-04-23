---
title: 'CA3010: 코드에서 XAML 삽입 취약성에 대해 검토합니다.'
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
ms.openlocfilehash: ea53f5e0cddf1dc6c6caf4c7fcfb79af52ce354e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60103695"
---
# <a name="ca3010-review-code-for-xaml-injection-vulnerabilities"></a>CA3010: 코드에서 XAML 삽입 취약성에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForXamlInjectionVulnerabilities|
|CheckId|CA3010|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청에 도달 하면 입력을 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 메서드를 로드 합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력에서 작업할 때 XAML 삽입 공격에 주의 해야 합니다. XAML은 개체 인스턴스화 및 실행을 직접적으로 나타내는 태그 언어입니다. 즉, XAML에서 만든 요소는 시스템 리소스 (예를 들어, 네트워크 액세스 및 파일 시스템 IO)와 상호 작용할 수 있습니다. 공격자에 대 한 입력을 제어할 수 있는 경우는 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 공격자가 코드를 실행할 수 있습니다 다음 메서드 호출을 로드 합니다.

이 규칙에 도달 하는 HTTP 요청에서 입력을 찾으려고 시도 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 메서드를 로드 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 XAML을 로드 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

신뢰할 수 없는 XAML 로드 되지 마십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 건너뛰지 않음.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] bytes = Convert.FromBase64String(input);
        MemoryStream ms = new MemoryStream(bytes);
        System.Windows.Markup.XamlReader.Load(ms);
    }
}
```

```vb
Imports System
Imports System.IO

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim bytes As Byte() = Convert.FromBase64String(input)
        Dim ms As MemoryStream = New MemoryStream(bytes)
        System.Windows.Markup.XamlReader.Load(ms)
    End Sub
End Class
```
