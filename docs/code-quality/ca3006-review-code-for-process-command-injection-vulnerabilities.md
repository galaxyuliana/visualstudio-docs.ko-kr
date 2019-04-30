---
title: 'CA3006: 코드에서 프로세스 명령 주입 취약점에 대해 검토합니다.'
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
ms.openlocfilehash: da161e611ca1d802c8da16370907029233bfd785
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806513"
---
# <a name="ca3006-review-code-for-process-command-injection-vulnerabilities"></a>CA3006: 코드에서 프로세스 명령 주입 취약점에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForProcessCommandInjectionVulnerabilities|
|CheckId|CA3006|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 처리 명령을 도달합니다.

## <a name="rule-description"></a>규칙 설명

신뢰할 수 없는 입력에서 작업할 때는 명령 삽입 공격에 주의 해야 합니다. 명령 삽입 공격, 보안 및 서버의 무결성을 손상 시 키 지 기본 운영 체제에 악의적인 명령이 실행할 수 있습니다.

이 규칙은 입력 처리 명령을 도달 하는 HTTP 요청을 찾으려고 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 프로세스를 시작 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능한 경우 사용자 입력을 기반으로 하는 프로세스를 시작 하지 마십시오.
- 알려진된 안전한 집합의 문자 및 길이 대해 입력의 유효성을 검사 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

입력의 유효성을 검사 되었거나 안전 이스케이프를 알고 있으면이 경고를 표시 하지 않으려면 안전 합니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.Diagnostics;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Process p = Process.Start(input);
    }
}
```

```vb
Imports System
Imports System.Diagnostics

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs as EventArgs)
        Dim input As String = Me.Request.Form("in")
        Dim p As Process = Process.Start(input)
    End Sub
End Class
```
