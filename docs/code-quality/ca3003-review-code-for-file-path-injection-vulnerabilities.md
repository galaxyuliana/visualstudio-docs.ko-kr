---
title: 'CA3003: 코드에서 파일 경로 삽입 취약성에 대해 검토합니다.'
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
ms.openlocfilehash: c20d3efb9ea84a7e8bb22288303313ef44b2b795
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806565"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003: 코드에서 파일 경로 삽입 취약성에 대해 검토합니다.

|||
|-|-|
|TypeName|ReviewCodeForFilePathInjectionVulnerabilities|
|CheckId|CA3003|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

신뢰할 수 없는 HTTP 요청 입력 파일 작업의 경로 도달합니다.

## <a name="rule-description"></a>규칙 설명

웹 요청에서 신뢰할 수 없는 입력에서 작업할 때 파일의 경로 지정 하는 경우에 입력 사용자 제어를 사용 하 여 주의 해야 합니다. 중요 한 데이터 유출의 결과 공격자가 의도 하지 않은 파일을 읽을 수 수 있습니다. 또는 다른 중요 한 데이터의 무단된 수정 등 서버의 보안을 손상 시 키 지는 공격자가 의도 하지 않은 파일을 쓸 수 있을 수 있습니다. 공격자가 가장 일반적인 방법은 됩니다 [경로 통과](https://www.owasp.org/index.php/Path_Traversal) 의도 한 디렉터리의 외부 파일에 액세스 하 합니다.

이 규칙은 입력 파일 작업에 경로 도달 하는 HTTP 요청을 찾으려고 합니다.

> [!NOTE]
> 이 규칙은 어셈블리 간에 데이터를 추적할 수 없습니다. 예를 들어, 하나의 어셈블리 HTTP 요청 입력을 읽고 하 다음 파일에 기록 하는 다른 어셈블리에 전달 하는 경우이 규칙 경고를 생성 하지 않습니다.

> [!NOTE]
> 이 규칙 메서드 호출에서 데이터 흐름은 분석 깊이에 구성할 수 있는 제한이 있습니다. 참조 [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) 에서 제한을 구성 하는 방법에 대 한 `.editorconfig` 파일입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 가능한 경우 명시적으로 알려진된 안전한 목록에 사용자 입력을 기반으로 하는 파일 경로 제한 합니다.  예를 들어, 응용 프로그램 에서만 액세스 해야 "red.txt", "green.txt" 또는 "blue.txt" 하는 경우 해당 값만 허용 합니다.
- 신뢰할 수 없는 파일 이름에 대 한 확인 하 고 이름을 제대로 구성 되었는지 확인 합니다.
- 경로 지정 하는 경우 전체 경로 이름을 사용 합니다.
- Path 환경 변수 등 잠재적으로 위험한 구문은 피하십시오.
- 긴 파일 이름을 허용 하 고 사용자의 짧은 이름을 제출 하는 경우 긴 이름의 유효성을 검사 합니다.
- 유효한 문자에 대 한 최종 사용자 입력을 제한 합니다.
- 이름의 길이가 MAX_PATH 길이 초과 하는 위치를 거부 합니다.
- 문자 그대로 해석 없이 파일을 처리 합니다.
- 파일 이름 파일 또는 장치를 나타내는지 여부를 결정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이전 섹션에 설명 된 대로 입력을 확인 했으면,이 경고를 표시 하지 않아도 괜찮습니다.

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userInput = Request.Params["UserInput"];
        // Assume the following directory structure:
        //   wwwroot\currentWebDirectory\user1.txt
        //   wwwroot\currentWebDirectory\user2.txt
        //   wwwroot\secret\allsecrets.txt
        // There is nothing wrong if the user inputs:
        //   user1.txt
        // However, if the user input is: 
        //   ..\secret\allsecrets.txt
        // Then an attacker can now see all the secrets.

        // Avoid this:
        using (File.Open(userInput, FileMode.Open))
        {
            // Read a file with the name supplied by user
            // Input through request's query string and display 
            // The content to the webpage. 
        }
    }
}
```

```vb
Imports System
Imports System.IO

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim userInput As String = Me.Request.Params("UserInput")
        ' Assume the following directory structure:
        '   wwwroot\currentWebDirectory\user1.txt
        '   wwwroot\currentWebDirectory\user2.txt
        '   wwwroot\secret\allsecrets.txt
        ' There is nothing wrong if the user inputs:
        '   user1.txt
        ' However, if the user input is: 
        '   ..\secret\allsecrets.txt
        ' Then an attacker can now see all the secrets.

        ' Avoid this:
        Using File.Open(userInput, FileMode.Open)
            ' Read a file with the name supplied by user
            ' Input through request's query string and display 
            ' The content to the webpage. 
        End Using
    End Sub
End Class
```
