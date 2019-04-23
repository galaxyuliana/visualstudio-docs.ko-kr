---
title: 'CA3004: 코드에서 정보 공개 취약성에 대해 검토합니다.'
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
ms.openlocfilehash: 82f763d9a6b1ec27975aa80054456a6bbbaeaa2b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069030"
---
# <a name="ca3004-review-code-for-information-disclosure-vulnerabilities"></a>CA3004: 코드에서 정보 공개 취약성에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForInformationDisclosureVulnerabilities|
|CheckId|CA3004|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

예외 메시지, 스택 추적 또는 문자열 표현을 웹 출력에 도달합니다.

## <a name="rule-description"></a>규칙 설명

공격자가 도움이 될 수 있는 프로그램의 내부 구조에 대 한 정보 찾기 다른 취약점을 악용 하는 공격자가 제공 예외 정보를 공개 합니다.

이 규칙 예외 메시지, 스택 추적 또는 HTTP 응답에 출력 되는 문자열 표현을 찾으려고 시도 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 예외를 catch 하 다음 예외를 출력 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

HTTP 응답에 예외 정보를 출력 하지 마십시오. 대신, 일반 오류 메시지를 제공 합니다. 참조 [OWASP의 오류 처리 페이지](https://www.owasp.org/index.php/Error_Handling) 자세한 지침에 대 한 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

알고 있는 경우 웹 출력 응용 프로그램의 트러스트 경계 내에서 이며 외부 노출 되지 확인이 경고를 표시 하지 않으려면입니다. 이 거의 없습니다. 응용 프로그램의 신뢰 경계 및 데이터 흐름은 시간이 지남에 따라 변경 될 수 있는 고려해 야 합니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write(e.ToString());
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write(e.ToString())
        End Try
    End Sub
End Class
```

### <a name="solution"></a>솔루션

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write("An error occurred. Please try again later.");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write("An error occurred. Please try again later.")
        End Try
    End Sub
End Class
```