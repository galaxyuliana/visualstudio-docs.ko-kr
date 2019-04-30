---
title: 팁과 요령 디버거에서
description: Visual Studio 디버거를 지 원하는 알려지지 않은 기능 중 일부에 대해 알아봅니다
ms.custom: seodec18
ms.date: 06/15/2018
ms.topic: conceptual
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 5262d8b1-2648-429e-85d5-90fcaadfb362
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b4c763ff31c6c62a177c77f8886f1de305a5170
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62853045"
---
# <a name="learn-productivity-tips-and-tricks-for-the-debugger-in-visual-studio"></a>For the Debugger in Visual Studio 생산성 팁과 트릭 배우기

Visual Studio 디버거에 대 한 몇 가지 생산성 팁과 요령에 알아보려면이 항목을 읽습니다. 디버거의 기본 기능을 보려면을 참조 하세요 [디버거 소개](../debugger/debugger-feature-tour.md)합니다. 이 항목에서는 기능 둘러보기에 포함 되지 않은 일부 영역을 설명 합니다.

## <a name="pin-data-tips"></a>고정 데이터 팁

자주을 마우스로 가리키면 데이터 팁 디버깅 하는 동안 하는 경우에 직접 빠른 액세스를 부여할 변수에 대 한 데이터 팁을 고정 하는 것이 좋습니다. 변수를 다시 시작 후에 고정 된 상태로 유지 됩니다. 데이터 팁을 고정 하려면 위에 마우스로 이동 하는 동안 고정 아이콘을 클릭 합니다. 여러 변수를 고정할 수 있습니다.

![고정 데이터 팁](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

## <a name="edit-your-code-and-continue-debugging-c-vb-c"></a>코드를 편집 하 고 계속 디버깅 (C#, VB, C++)

Visual Studio에서 지 원하는 대부분의 언어에서 디버깅 세션 중에 코드를 편집할 수 있으며 디버깅을 계속할 수 있습니다. 디버거, 확인 편집 및 키를 눌러 일시 중지 된 동안 커서를 사용 하 여 코드에이 기능을 사용 하려면를 클릭 **F5**, **F10**, 또는 **F11** 디버깅을 계속 합니다.

![편집 및 디버깅을 계속할](../debugger/media/dbg-tips-edit-and-continue.gif "EditAndContinue")

자세한 내용은 기능 제한 사항 및 기능을 사용 하 여 [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="debug-issues-that-are-hard-to-reproduce"></a>재현 하기 어려운 문제 디버그

어렵거나를 앱의 특정 상태를 다시 만드는 시간이 많이 걸리는 인 경우에 지 여부를 조건부 중단점을 사용 하는 데 도움이 하는 것이 좋습니다. 사용할 수 있습니다 [조건부 중단점](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) 앱 (예: 변수에서 잘못 된 데이터를 저장 하는 상태) 원하는 상태가 될 때까지 앱 코드에 중단을 방지 하려면 중단점을 필터링 합니다. 식, 필터, 적중된 횟수 및 등을 사용 하 여 조건을 설정할 수 있습니다.

#### <a name="to-create-a-conditional-breakpoint"></a>조건부 중단점을 만들려면

1. 선택한 중단점 아이콘 (빨간 공이)를 마우스 오른쪽 단추로 클릭 **조건을**합니다.

2. 에 **중단점 설정** 창에서 식 입력 합니다.

    ![조건부 중단점](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

3. 다른 유형의 조건에 관심이 선택 **필터** 대신 **조건식** 에 **중단점 설정** 대화 상자를 닫은 후 다음을 필터 팁입니다.

## <a name="configure-the-data-to-show-in-the-debugger"></a>디버거에서 표시할 데이터를 구성 합니다.

에 대 한 C#, Visual Basic 및 C++ (C++/CLI 코드에만 해당), 디버거를 사용 하 여 표시할 정보를 알 수 있습니다 합니다 [DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md) 특성. 에 대 한 C++ 코드에서 동일한 사용 하 여 수행할 수 있습니다 [Natvis 시각화](create-custom-views-of-native-objects.md)합니다.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

디버거를 사용 하 여 마우스를 사용 하 여 왼쪽의 노란색 화살표 포인터를 가져올 코드 줄에서 일시 중지 합니다. 코드 실행 경로에 다른 시점에 노란색 화살표 포인터를 이동 합니다. 사용 하 여 F5 또는 단계별 실행 명령을 계속 앱을 실행 합니다.

![실행 포인터를 이동](../debugger/media/dbg-tour-move-the-execution-pointer.gif "실행 포인터를 이동 합니다.")

실행 흐름을 변경하면 디버거를 다시 시작하지 않고도 다른 코드 실행 경로를 테스트하거나 코드를 다시 실행하는 등의 작업을 수행할 수 있습니다.

> [!WARNING]
> 이 기능을 주의 깊게 사용해야 하는 경우가 많으며 도구 설명에 경고가 표시됩니다. 다른 경고도 표시될 수 있습니다. 포인터를 이동 하면 앱을 이전 응용 프로그램 상태를 되돌릴 수 없습니다.

## <a name="track-an-out-of-scope-object-c-visual-basic"></a>추적 범위를 벗어나는 개체 (C#, Visual Basic)

같은 디버거 창을 사용 하 여 변수를 표시 하는 것이 간단 합니다 **조사식** 창입니다. 그러나 경우 변수 범위를 벗어날에 **조사식** 창 표시 될 수도 있습니다는 회색으로 표시 합니다. 일부 앱 시나리오에서 변수의 값도 변수가 범위를 벗어날 시점과 밀접 하 게 시청 하려는 경우 변경할 수 있습니다 (예를 들어 변수로 발생할 수 가비지 수집). 개체 ID를 만들어 변수를 추적할 수 있습니다 합니다 **조사식** 창입니다.

#### <a name="to-create-an-object-id"></a>개체 ID를 만들려면

1. 추적 하려는 변수에 중단점을 설정 합니다.

2. 디버거를 시작 합니다 (**F5**) 중단점에서 중지 합니다.

3. 변수를 찾을 합니다 **지역** 창 (**디버그 > Windows > 지역**), 변수를 마우스 오른쪽 단추로 **개체 ID 만들기**합니다.

    ![개체 ID를 만듭니다](../debugger/media/dbg-tips-watch-create-object-id.png "CreateObjectID")

4. **$** 창에 **지역** 창을 닫습니다. 이 변수는 개체 id입니다.

5. 개체 ID 변수를 마우스 오른쪽 단추로 클릭 하 고 선택 **조사식 추가**합니다.

자세한 내용은 [개체 ID 만들기](../debugger/watch-and-quickwatch-windows.md#bkmk_objectIds)합니다.

## <a name="view-return-values-for-functions"></a>함수에 대 한 반환 값 보기

함수에 대 한 반환 값을 보려면에 표시 되는 함수를 조사 합니다 **자동** 코드를 단계별로 동안 창입니다. 함수의 반환 값을 보려면 원하는 함수를 이미 실행 되었는지 확인 (키를 눌러 **F10** 함수 호출에 현재 중지 된 경우 한 번). 사용 하 여 창이 닫혀 있는 경우 **디버그 > Windows > 자동** 열려는 합니다 **자동** 창.

![Autos Window](../debugger/media/dbg-tips-autos-window.png "AutosWindow")

또한 함수를 입력할 수 있습니다 합니다 **직접 실행** 반환 값 보기 창입니다. (사용 하 여 엽니다 **디버그 > Windows > 직접 실행**.)

![직접 실행 창](../debugger/media/dbg-tips-immediate-window.png "ImmediateWindow")

사용할 수도 있습니다 [의사 변수](../debugger/pseudovariables.md) 에 **조사식** 및 **직접 실행** 창 같은 `$ReturnValue`합니다.

## <a name="string_visualizer"></a>시각화 도우미에서 문자열을 검사 합니다.

문자열을 사용 하는 경우 전체 형식이 지정 된 문자열을 볼 수 있습니다. 일반 텍스트, XML, HTML 또는 JSON 문자열을 보려면 돋보기 아이콘을 클릭 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 아이콘") 문자열 값을 포함 하는 변수를 가리킬 때.

![문자열 시각화 도우미를 열려면](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

문자열 시각화 도우미를 문자열 형식에 따라 잘못 된 형식의 문자열 인지 확인 도움이 될 수 있습니다. 예를 들어, blank **값** 필드 문자열 시각화 도우미 형식을 인식 하지 못하는 것을 나타냅니다. 자세한 내용은 [문자열 시각화 도우미 대화 상자](../debugger/string-visualizer-dialog-box.md)합니다.

![JSON 문자열 시각화 도우미](../debugger/media/dbg-tips-string-visualizer-json.png "JSONStringVisualizer")

디버거 창에 표시 된 DataSet 및 DataTable 개체와 같은 몇 가지 다른 형식에 대 한 기본 제공 시각화 도우미를 열 수도 있습니다.

## <a name="break-into-code-on-handled-exceptions"></a>처리 된 예외에서 코드 중단

디버거가 처리 되지 않은 예외에서 코드를 중단 합니다. 그러나 예외를 처리 (내에서 발생 하는 예외와 같은 `try/catch` 블록) 버그의 원인이 될 수도 있습니다 및 경우를 조사 하는 것이 좋습니다. 옵션을 구성 하 여 뿐만 아니라 처리 된 예외에 대 한 코드를 중단 하도록 디버거를 구성할 수 있습니다 합니다 **예외 설정** 대화 상자. 선택 하 여이 대화 상자를 엽니다 **디버그 > Windows > 예외 설정**합니다.

합니다 **예외 설정** 대화 상자를 사용 하면 특정 예외에 대 한 코드를 중단 하도록 디버거에 지시할 수 있습니다. 아래 그림에서는 디버거가 코드로 중단 될 때마다는 `System.NullReferenceException` 발생 합니다. 자세한 내용은 [예외 관리](../debugger/managing-exceptions-with-the-debugger.md)합니다.

![예외 설정 대화 상자](../debugger/media/dbg-tips-exception-settings.png "ExceptionSettingsDialogBox")

## <a name="debug-deadlocks-and-race-conditions"></a>교착 상태 및 경합 상태를 디버그 합니다.

다중 스레드 응용된 프로그램에 공통 된 문제의 종류를 디버깅 하는 경우 종종 디버깅 하는 동안 스레드 위치를 볼 수 있습니다. 사용 하 여 쉽게 수행할 수 있습니다 합니다 **소스의 스레드 표시** 단추입니다.

#### <a name="to-show-threads-in-your-source-code"></a>소스 코드에서 스레드를 표시 하려면

1. 디버깅 하는 동안 클릭 합니다 **소스의 스레드 표시** 단추 ![소스의 스레드 표시](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker") 에 **디버그** 도구 모음입니다.

2. 창 왼쪽의 여백을 확인합니다. 이 줄에 표시 된 *스레드 마커* 아이콘 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker") 두 가닥의 실와 유사한 합니다. 스레드 마커는 이 위치에서 스레드가 중지되었음을 나타냅니다.

    스레드 마커 중단점에서 부분적으로 숨겨진 수를 확인 합니다.

3. 스레드 마커에 포인터를 올려 놓습니다. DataTips가 나타납니다. DataTip을 통해 중지된 각 스레드의 이름과 스레드 ID 번호를 알 수 있습니다.

    스레드 위치를 볼 수도 있습니다는 [병렬 스택 창의](../debugger/get-started-debugging-multithreaded-apps.md)합니다.

## <a name="examine-payloads-for-web-services-and-network-resources-uwp"></a>웹 서비스 및 네트워크 리소스 (UWP)에 대 한 페이로드를 검토 합니다.

UWP 앱에서 사용 하 여 수행 된 네트워크 작업을 분석할 수 있습니다는 `Windows.Web.Http` API. 웹 서비스 및 네트워크 리소스를 디버깅 하는 데이 도구를 사용할 수 있습니다. 도구를 사용 하려면 선택 **디버그 > 성능 Profiler**합니다. 선택 **네트워크**를 선택한 후 **시작**합니다. 앱에서 `Windows.Web.Http`를 사용하는 시나리오를 확인한 다음 **컬렉션 중지**를 선택하여 보고서를 생성합니다.

![네트워크 사용량 프로 파일링 도구](../profiling/media/prof-tour-network-usage.png "NetworkUsageProfTool")

요약 뷰에서 작업을 선택하여 세부 정보를 확인할 수 있습니다.

![네트워크 사용량 도구에서 자세한](../profiling/media/prof-tour-network-usage-details.png "DetailedViewNetworkUsage")

자세한 내용은 [네트워크 사용량](../profiling/network-usage.md)을 참조하세요.

## <a name="modules_window"></a> 디버거가 앱에 연결 하는 방법에 대해 get (C#, C++, Visual Basic의 경우 F#)

를 실행 중인 앱에 연결 하려면 디버거에서 디버그 하려는 앱의 정확히 동일한 빌드에 대해 생성 되는 기호 (.pdb) 파일을 로드 합니다. 일부 시나리오에서는 기호 파일의 간단한 기술 유용할 수 있습니다. Visual Studio를 사용 하 여 기호 파일을 로드 하는 방법을 검사할 수 있습니다 합니다 **모듈** 창입니다.

엽니다는 **모듈** 를 선택 하 여 디버깅 하는 동안 창 **디버그 > Windows > 모듈**합니다. 합니다 **모듈** 창 디버거가 사용자 코드를 처리 하는 어떤 모듈 알 수 또는 [ *내 코드만*](../debugger/just-my-code.md), 모듈에 대 한 상태를 로드 하는 기호입니다. 대부분의 시나리오에서 디버거가 사용자 코드에 대 한 기호 파일을 자동으로 검색 하지만 올바른 기호 파일 얻기 위해 추가 단계가 필요 한 단계씩 코드 실행 (또는 디버그).NET framework 코드, 시스템 코드 또는 타사 라이브러리 코드 하려는 경우.

![모듈 창에서 기호 정보를 볼](../debugger/media/dbg-tips-modules-window.png "ViewSymbolInformation")

직접 기호 정보를 로드할 수 있습니다 합니다 **모듈** 창을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 **기호 로드**합니다.

경우에 따라 앱 개발자는 일치 하는 기호 파일 (좁히는), 릴리스 버전 나중에 디버깅 수 있도록 일치 하는 기호의 복사본 빌드에 대 한 파일 유지 하지만 없이 앱을 배송 됩니다.

디버거가 사용자 코드와 코드를 분류 하는 방법을 알아보려면, 참조 [Just My Code](../debugger/just-my-code.md)합니다. 기호 파일에 대 한 자세한 내용을 참조 하세요 [Visual Studio 디버거에서 기호 (.pdb) 및 원본 파일 지정](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다.

## <a name="learn-more"></a>자세한 정보

추가 팁 및 요령 및 자세한 내용은 다음 블로그 게시물을 참조 하세요.

- [Visual Studio에서 디버깅을 위해 더 적은 알려진된 해킹을 7](https://devblogs.microsoft.com/visualstudio/7-lesser-known-hacks-for-debugging-in-visual-studio/)
- [Visual Studio에서 7 숨겨진된 보석](https://devblogs.microsoft.com/visualstudio/7-hidden-gems-in-visual-studio-2017/)

## <a name="see-also"></a>참고 항목
[바로 가기 키](../ide/tips-and-tricks-for-visual-studio.md)
