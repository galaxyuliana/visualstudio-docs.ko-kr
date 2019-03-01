---
title: 출력 창에 메시지 보내기 | Microsoft Docs
ms.date: 11/08/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb4493eb55b83b9f76d1a833ba2df359ae9683e8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682507"
---
# <a name="send-messages-to-the-output-window"></a>출력 창으로 메시지 보내기

런타임 메시지를 작성할 수 있습니다는 **출력** 사용 하 여 창을 합니다 <xref:System.Diagnostics.Debug> 클래스 또는 <xref:System.Diagnostics.Trace> 구성 요소인 클래스의는 <xref:System.Diagnostics> 클래스 라이브러리입니다. 사용 합니다 <xref:System.Diagnostics.Debug> 의 출력만 하려는 경우 클래스는 *디버그* 프로그램의 버전입니다. 사용 합니다 <xref:System.Diagnostics.Trace> 둘 다에서 출력 하려는 경우 클래스를 *디버그* 및 *릴리스* 버전입니다.

## <a name="output-methods"></a>출력 메서드
 <xref:System.Diagnostics.Trace> 클래스와 <xref:System.Diagnostics.Debug> 클래스에는 다음과 같은 출력 메서드가 있습니다.

- 실행을 중단하지 않고 정보를 출력하는 여러 가지 `Write` 메서드. 이 메서드는 이전 Visual Basic 버전의 `Debug.Print` 메서드 대신 사용됩니다.

- <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 메서드를 지정된 된 조건이 실패할 경우 실행 및 출력 정보를 중단 합니다. 기본적으로 `Assert` 메서드는 해당 정보를 대화 상자에 표시합니다. 자세한 내용은 [관리 코드의 어설션](../debugger/assertions-in-managed-code.md)을 참조하세요.

- <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 메서드를 항상 실행 및 출력 정보를 중단 합니다. 기본적으로 `Fail` 메서드는 정보를 대화 상자에 표시합니다.

합니다 **출력** 창에 대 한 정보를 표시할 수도 있습니다.

- 디버거에서 로드하거나 언로드한 모듈 정보

- throw된 예외 정보

- 종료되는 프로세스 정보

- 종료되는 스레드 정보

## <a name="see-also"></a>참고 항목
- [디버거 보안](../debugger/debugger-security.md)
- [출력 창](../ide/reference/output-window.md)
- [추적 및 계측 응용 프로그램](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)
- [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [관리 코드 디버깅](../debugger/debugging-managed-code.md)
