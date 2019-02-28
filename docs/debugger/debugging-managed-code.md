---
title: 관리 코드 디버깅 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 14dc53413f646718b85ec9ea43d968dc9f64a96f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719319"
---
# <a name="debugging-managed-code"></a>관리 코드 디버깅

이 단원에서는 Visual Basic, C# 및 C++ 등 공용 언어 런타임을 대상으로 하는 언어로 작성된 관리되는 응용 프로그램의 일반적인 디버깅 문제와 기술에 대해 설명합니다. 이 단원에서 설명하는 기술은 높은 수준의 기술입니다. [디버거 소개](../debugger/debugger-feature-tour.md)

## <a name="in-this-section"></a>섹션 내용

[출력 창의 진단 메시지](../debugger/diagnostic-messages-in-the-output-window.md) 에 대해 설명 합니다는 <xref:System.Diagnostics.Debug> 하 고 <xref:System.Diagnostics.Trace> 클래스는 런타임에 메시지를 작성할 수 있습니다는 **출력** 창. 이러한 클래스에는 실행을 중단하지 않고 정보를 출력하는 출력 메서드와 지정된 조건이 실패할 경우 실행을 중단하고 정보를 출력하는 출력 메서드가 포함되어 있습니다.

[관리 코드의 어설션](../debugger/assertions-in-managed-code.md) 설명에 대 한 인수로 지정 하는 조건을 테스트 하는 관리 코드에 어설션 `Assert` 메서드. 또한 예제 코드, <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스 메서드의 사용 정보, 코드의 디버그 및 릴리스 버전에 대한 고려 사항, 의도하지 않은 연산, 어설션 인수, 어설션 동작 사용자 지정, 구성 파일 등의 내용을 제공합니다.

[Visual Basic의 stop 문](../debugger/stop-statements-in-visual-basic.md) 에 대해 설명 합니다는 `Stop` 중단점을 설정 하는 대신 제공 하는 문입니다. `Stop` 문과 `End` 문을 비교하고 `Stop` 문과 `Assert` 문을 비교하여 살펴볼 뿐만 아니라 예제 코드도 제공합니다.

[연습: Windows Form 디버깅](../debugger/walkthrough-debugging-a-windows-form.md) Windows Form 만들기 및 구성 하는 디버깅에 대 한 단계별 지침을 제공 합니다. 관리되는 Windows 응용 프로그램의 표준 구성 요소인 Windows Form은 가장 일반적인 형태의 관리되는 응용 프로그램 중 하나입니다. 이 연습에서는 Visual C#과 Visual Basic을 사용하지만 C++로 Windows Form을 만드는 방법도 대체로 비슷합니다.

[OnStart 메서드 디버깅](../debugger/how-to-debug-the-onstart-method.md) 디버그할 수 있도록 코드 예제를 제공 합니다 `OnStart` 메서드의 관리 되는 Windows 서비스입니다. Windows 서비스의 `OnStart` 메서드를 디버깅하려면 몇 줄의 코드를 추가하여 서비스를 시뮬레이션해야 합니다.

[혼합 모드 디버깅](../debugger/debugging-mixed-mode-applications.md) 혼합 모드 응용 프로그램 디버깅에 대해 설명 합니다. 혼합 모드 응용 프로그램은 네이티브 코드와 관리 코드가 결합된 응용 프로그램입니다.

[오류: 디버깅 불가능 시스템에 커널 디버거가 사용 중 이므로](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md) 에서 관리 되는 코드를 디버깅 하려고 하면 발생 하는 오류 메시지를 설명 된 [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], 또는 Windows NT 시스템 디버그 모드에서 시작 된 합니다.

[JIT 최적화 및 디버깅](../debugger/jit-optimization-and-debugging.md) 디버깅 JIT 최적화의 효과 설명 합니다.

[LINQ 및 DLINQ 디버깅](../debugger/debugging-linq.md) LINQ 쿼리를 디버깅 하는 것에 대 한 기술에 설명 합니다.

[연습: 병렬 응용 프로그램을 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md) 를 사용 하는 방법에 설명 합니다 **병렬 작업** 및 **병렬 스택** 병렬 응용 프로그램을 디버깅 하는 windows 도구입니다.

## <a name="related-sections"></a>관련 단원

[IntelliTrace](../debugger/intellitrace.md) IntelliTrace 사용 하 여 앱의 실행 기록을 기록 하 여 빠르고 쉽게 버그를 찾습니다. 기록된 이벤트 및 호출에서 앞뒤로 이동하며 주요 시점의 응용 프로그램 상태를 확인합니다. 여러 중단점을 설정하거나 자주 응용 프로그램을 다시 시작하지 않고 코드를 디버깅합니다. Visual Studio Enterprise에 필요합니다.

[추적 및 응용 프로그램을 계측](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications) 코드의 전략적 위치에 trace 문 배치에서는 실행 하 고 계측, 응용 프로그램의 실행을 모니터링 하는 방법을 추적 하는 방법을 설명 합니다입니다. 이 항목에서는 계측 및 추적, 추적 스위치, 추적 수신기, 응용 프로그램의 코드 추적, 응용 프로그램 코드에 추적 문 추가, <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace>를 사용하는 조건부 컴파일 등을 소개하는 정보로 연결되는 링크도 제공합니다.

[/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) 를 추가 하는 링커 옵션을 설명 <xref:System.Diagnostics.DebuggableAttribute> c + +로 작성 된 코드입니다. 이 특성은 C++를 사용한 연결 등의 디버깅 기능을 사용하는 데 필요합니다.

[Windows 서비스 응용 프로그램 디버깅](/dotnet/framework/windows-services/how-to-debug-windows-service-applications) Windows 서비스 응용 프로그램 디버깅, 설정 하는 등, 프로세스에 연결, 서비스의 코드 디버깅에 대 한 고려 사항을 제공 `OnStart` 메서드와 기본에서 코드 메서드, 중단점 설정, 서비스 제어 관리자를 사용 하 여을 시작 하려면 중지, 일시 중지 하 고 서비스를 계속 합니다.

[디버깅 및 프로 파일링](/dotnet/framework/debug-trace-profile/index) .NET Framework에 대 한 응용 프로그램을 디버깅 및 구성 요구 사항에 설명 합니다.

[스크립트 및 웹 응용 프로그램을 디버깅](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications) 일반적인 디버깅 문제와 기술 스크립트 및 웹 응용 프로그램을 디버깅할 때 발생할 수는 방법을 설명 합니다.

[Visual Studio 2015 디버거의 새로운 기능](../debugger/what-s-new-for-the-debugger-in-visual-studio.md) 의이 릴리스에서 추가 된 새로운 디버깅 기능 설명은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.

[디버깅 홈 페이지](../debugger/debugger-feature-tour.md) 의 디버깅 설명서 단원에 대 한 링크를 제공 합니다. 이 정보에는 디버거의 새로운 기능, 설정 및 준비, 중단점, 예외 처리, 편집 및 계속, 관리 코드 디버깅, Visual C++ 프로젝트 디버깅, COM 및 ActiveX 디버깅, DLL 디버깅, SQL 디버깅, 사용자 인터페이스 참조 등이 포함됩니다.

## <a name="see-also"></a>참고 항목

[연습: 디자인 타임에 컨트롤을 Forms 사용자 지정 Windows 디버깅](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
[디버거 보안](../debugger/debugger-security.md)
[Visual Studio에서 디버깅](../debugger/index.md) 
 [ 디버거 소개](../debugger/debugger-feature-tour.md)