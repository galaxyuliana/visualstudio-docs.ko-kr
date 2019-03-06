---
title: 디버거로 코드 탐색 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/12/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.execution
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 759072ba-4aaa-447e-8e51-0dd1456fe896
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05458481a691f74f1746860e537d915dcad90efc
ms.sourcegitcommit: cdcbf254db737d42275e95de4ffc4f8c14e87e00
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57428754"
---
# <a name="navigate-through-code-with-the-visual-studio-debugger"></a>Visual Studio 디버거로 코드 탐색

Visual Studio 디버거는 앱의 상태를 검사 하 고 해당 실행 흐름을 표시 하는 코드를 탐색할 수 있습니다. 검사 하려는 코드에 신속 하 게 바로 가기 키, 디버그 명령, 중단점 및 기타 기능을 사용할 수 있습니다. 디버거 탐색 명령 및 바로 가기를 사용 경험을 사용 하 여 빠르고 쉽게 찾아서 앱 문제를 해결할 수 있도록 합니다.  읽을 하려는 처음 코드를 디버그 하려는 경우 [초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md) 하 고 [기술 및 도구 디버깅](../debugger/write-better-code-with-visual-studio.md) 이 문서를 진행 하기 전에 합니다.

## <a name="basic-debugging"></a>기본적인 디버깅

디버거가 연결 된 앱을 시작 하려면 키를 누릅니다 **F5**를 선택 **디버그** > **디버깅 시작**, 또는 Visual Studio 도구 모음에서 녹색 화살표를 선택 합니다.

 ![DBG&#95;Basics&#95;Start&#95;Debugging](../debugger/media/dbg_basics_start_debugging.png "DBG_Basics_Start_Debugging")

디버그 하는 동안 노란색 강조 표시는 다음을 실행 하는 코드 줄을 표시 합니다.

 ![DBG&#95;기본 사항&#95;중단&#95;모드](../debugger/media/dbg_basics_break_mode.png "중단 모드")

대부분의 windows를 같은 디버거 합니다 **모듈** 및 **조사식** 디버거가 실행 되는 동안에 windows에서 사용할 수 있습니다. 일부 디버거에서 변수 값을 보는 등의 기능을 합니다 **지역** 창 또는에서 식을 계산 합니다 **조사식** 창, 라고도 하는 중단점에서 디버거가 일시 중지 하는 동안에 사용할 수 있습니다 *중단 모드*합니다.

중단 모드에서 함수, 변수, 하는 동안 앱 실행이 일시 중단 하 고 개체가 메모리에 남아 있습니다. 요소의 위치와 상태 위반이 나 버그를 확인할 수 있습니다. 일부 프로젝트 유형의 경우에 중단 모드에서 응용 프로그램을 조정할을 만들 수 있습니다. 이러한 기능을 보여 주는 비디오를 참조 하세요 [디버거를 사용 하 여 시작](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6)합니다.

소스 또는 기호 없는 코드에서 중단 하는 경우 (*.pdb*) 파일이 로드 디버거 표시를 **원본 파일이 없습니다** 하거나 **기호를 찾을 수 없습니다** 도움이 될 수 있는 페이지 파일 찾기 및 로드 합니다. [기호 파일(.pdb) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)을 참조하세요. 기호 또는 소스 파일을 로드할 수 없습니다, 하는 경우의 어셈블리 지침 계속 디버깅할 수 있습니다 합니다 **디스어셈블리** 창입니다.

항상 시작 부분에 앱을 시작 하 여 디버깅을 시작할 필요가 없습니다. 누를 수도 있습니다 **F11** 에 [코드로 단계](#BKMK_Step_into__over__or_out_of_the_code), 키를 누릅니다 **F10** 에 [코드 건너뛰기](#BKMK_Step_over_Step_out), 또는 [특정 위치까지 실행 또는 함수](#BKMK_Break_into_code_by_using_breakpoints_or_Break_All)합니다.

##  <a name="step-through-code"></a>단계별 코드 실행

디버거 단계 명령을 쉽게 앱 상태를 검사할 해당 실행 흐름에 대해 자세히 알아봅니다.

앱의 진입점을 찾을 해야 할 경우 시작 **F10** 하거나 **F11**합니다.

### <a name="BKMK_Step_into__over__or_out_of_the_code"></a> 한 단계씩 코드 줄에서 코드 실행

디버깅 하는 동안 문이나 코드의 각 줄에서 중지 하려면 사용 **디버그** > **단계씩**, 누르거나 **F11**.

디버거는 코드 문 하지 실제 줄 안내 합니다. 예를 들어 한 줄에 `if` 절을 작성할 수 있습니다.

  ```csharp
  int x = 42;
  string s = "Not answered";
  if( int x == 42) s = "Answered!";
  ```

  ```vb
  Dim x As Integer = 42
  Dim s As String = "Not answered"
  If x = 42 Then s = "Answered!"
  ```

그러나이 줄 한 단계씩 실행할 때 디버거는 조건을 한 단계와 결과 다른 단계로 처리 합니다. 위의 예제에서는 조건이 true입니다.

중첩된 함수 호출인 경우 **한 단계씩 코드 실행** 명령은 가장 안쪽에 중첩된 함수를 한 단계씩 실행합니다. 예를 들어, 사용 하는 경우 **한 단계씩 코드 실행** 와 같은 호출에 `Func1(Func2())`, 디버거에서 함수를 단계별로 `Func2`합니다.

>[!TIP]
>변수를 해당 값을 확인 하거나 마우스로 가리키면 각 코드 줄을 실행 하는 [지역](autos-and-locals-windows.md) 및 [조사식](watch-and-quickwatch-windows.md) 변경 값을 조사 하려면 windows. 함수를 한 단계씩 실행 하는 동안 호출 스택을 시각적으로 추적할 수 있습니다. 참조 [디버깅 하는 동안 호출 스택의 메서드 매핑](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.

###  <a name="BKMK_Step_over_Step_out"></a> 코드를 통해 단계를 건너뛸 일부 함수

디버깅 하는 동안 함수에 대 한 중요 하지 않을 수 있습니다 또는 알고 작동 검증된 라이브러리 코드와 같은 합니다. 코드를 통해 표시 하지 않으려면 다음 명령을 사용할 수 있습니다. 함수는 계속 실행 되지만, 디버거는 해당 건너뜁니다.

|키보드 명령|디버그 메뉴 명령|설명|
|----------------------|------------------|-----------------|
|**F10**|**프로시저 단위 실행**|현재 줄에 함수 호출이 포함 되어 있으면 **프로시저 단위 실행** 코드를 실행 한 다음 호출된 된 함수가 반환 후 코드의 첫 번째 줄에서 실행을 일시 중단 합니다.|
|**Shift**+**F11**|**프로시저 나가기**|**프로시저 나가기** 계속 코드를 실행 하 고 현재 함수가 반환 될 때 실행을 일시 중단 합니다. 디버거는 현재 함수를 통해 건너뜁니다.|

##  <a name="BKMK_Break_into_code_by_using_breakpoints_or_Break_All"></a> 특정 위치 또는 함수까지 실행

정확 하 게 검사 하 고 원하는 코드를 알고 있는 경우 특정 위치 또는 함수에 직접 실행 하는 것이 좋습니다 또는 디버깅을 시작 하려는 위치를 알 수 있습니다.

### <a name="run-to-a-breakpoint-in-code"></a>코드의 중단점까지 실행

코드에 간단한 중단점을 설정 하려면 실행을 일시 중단 시킬 코드 줄 옆에 있는 맨 왼쪽된 여백을 클릭 합니다. 누릅니다 줄을 선택할 수도 있습니다 **F9**를 선택 **디버그** > **중단점 설정/해제**를 마우스 오른쪽 단추로 클릭 하 고 선택 또는 **중단점**  >  **중단점 삽입**합니다. 중단점이 코드 줄 옆에 있는 왼쪽된 여백에 빨간 점이 표시 됩니다. 줄은 실행 직전 디버거가 실행을 일시 중단 합니다.

![중단점 설정](../debugger/media/dbg_basics_setbreakpoint.png "중단점 설정")

Visual Studio에서 중단점은 조건부 중단점 및 추적점과 같은 다양한 추가 기능을 제공합니다. 자세한 내용은 참조 하세요 [중단점을 사용 하 여](../debugger/using-breakpoints.md)입니다.

### <a name="run-to-a-function-breakpoint"></a>함수 중단점까지 실행

지정된 된 함수에 도달할 때까지 실행 하도록 디버거에 지시할 수 있습니다. 함수 이름을 지정하거나 호출 스택에서 함수를 선택할 수 있습니다.

**함수 중단점 이름으로 지정 하려면**

1. 선택 **디버깅할** > **새 중단점** > **함수 중단점**

1. 에 **새 함수 중단점** 대화 상자에서 함수 이름을 입력 하 고 해당 언어를 선택 합니다.

   ![새 함수 중단점 대화 상자](../debugger/media/dbg_execution_newbreakpoint.png "새 함수 중단점")

1. **확인**을 선택합니다.

함수 오버 로드 되거나 둘 이상의 네임 스페이스에서 원하는 것을 선택할 수 있습니다 하는 경우는 **중단점** 창입니다.

![함수 중단점을 오버 로드](../debugger/media/dbg_execution_overloadedbreakpoints.png "함수 중단점을 오버 로드")

**호출 스택에서 함수 중단점을 선택 하려면**

1. 디버깅 하는 동안 열을 **호출 스택** 를 선택 하 여 창 **디버그** > **Windows** > **호출 스택**합니다.

1. 에 **호출 스택** 창 함수를 마우스 오른쪽 단추로 클릭 하 고 선택 **커서까지 실행**를 누르거나 **Ctrl**+**F10**합니다.

호출 스택을 시각적으로 추적을 참조 하세요 [디버깅 하는 동안 호출 스택의 메서드 매핑](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.

### <a name="run-to-a-cursor-location"></a>커서 위치까지 실행

소스 코드에서 커서 위치까지 실행 하려면 또는 **호출 스택** 창에서 중단을 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 선을 선택 **커서까지 실행**를 누르거나 **Ctrl** + **F10**합니다. 선택 **커서까지 실행** 은 임시 중단점 설정과 유사 합니다.

### <a name="run-to-click"></a>실행하려면 클릭

디버거에서 일시 중지 하는 동안에 소스 코드에서 문 마우스로 수 있습니다 또는 **디스어셈블리** 창과 선택 합니다 **여기까지 실행** 녹색 화살표 아이콘입니다. 사용 하 여 **실행 하려면 클릭** 임시 중단점을 설정할 필요가 없습니다.

![실행하려면 클릭](../debugger/media/dbg-run-to-click.png "실행하려면 클릭")

> [!NOTE]
> **실행 하려면 클릭** 부터 사용할 수 있습니다는 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

### <a name="manually-break-into-code"></a>수동으로 코드 중단

실행 중인 앱에서 코드의 사용 가능한 다음 줄에서 중단 하려면 **디버그** > **모두 중단**를 누르거나 **Ctrl**+**Alt**  + **중단**합니다.

##  <a name="BKMK_Set_the_next_statement_to_execute"></a> 실행 흐름 변경에 대 한 포인터를 이동 합니다.

디버거가 일시 중지 하는 동안 소스 코드의 여백에 있는 노란색 화살표 또는 **디스어셈블리** 창 실행한 다음 문으로의 위치를 표시 합니다. 이 화살표를 이동 하 여 실행한 다음 문을 변경할 수 있습니다. 코드의 일부를 건너뛸 수도 있고 이전 줄으로 반환할 수 있습니다. 포인터를 이동 하는 것은 알려진된 버그를 포함 하는 코드의 섹션을 건너 뛰 려는 경우에 유용 합니다.

 ![포인터를 이동](../debugger/media/dbg_basics_example3.gif "포인터를 이동")

다음에 실행할 문을 변경 하려면 디버거가 중단 모드 여야 합니다. 소스 코드에서 또는 **디스어셈블리** 창에서 다른 줄에 노란색 화살표를 끌어 옵니다. 또는 다음 실행 하 고 선택 하려는 줄을 마우스 오른쪽 단추로 클릭 **다음 문 설정**합니다.

프로그램 카운터 지점 실행 되지 않고 이전 및 새 실행 간의 새 위치 및 지침으로 직접 이동 합니다. 그러나 실행 위치를 뒤로 이동 하는 경우 중간 지침 취소할 수 없습니다.

>[!CAUTION]
>- 다음 문을 다른 함수나 범위로 이동하면 호출 스택이 손상되어 런타임 오류나 예외가 발생할 수 있습니다. 다음 문을 다른 범위로 이동하려고 하면 디버거에서 대화 상자가 열리고 여기서 작업을 취소할 수 있습니다.
>- Visual Basic의 경우 다음 문을 다른 범위나 함수로 이동할 수 없습니다.
>- 네이티브 C++에서 런타임 검사를 활성화한 경우 다음 문을 설정하면 실행이 메서드의 끝에 도달할 때 예외가 throw될 수 있습니다.
>- 편집하며 계속하기를 활성화한 경우 편집하며 계속하기에서 즉시 다시 매핑할 수 없는 종류의 편집을 수행하면 **다음 문 설정** 이 실패합니다. 예를 들어 catch 블록 내의 코드를 편집하면 이 문제가 발생합니다. 이 경우 오류 메시지는 작업이 지원 되지 않습니다 알려 줍니다.
>- 관리 코드에서 하는 경우 다음 문을 이동할 수 없습니다.
>   - 다음 문이 현재 문과 다른 메서드에 있는 경우
>   - Just In Time 여 디버깅을 시작한 디버깅 합니다.
>   - 호출 스택 해제 중입니다.
>   - System.StackOverflowException 또는 System.Threading.ThreadAbortException 예외가 throw된 경우

## <a name="BKMK_Restrict_stepping_to_Just_My_Code"></a>비 사용자 코드 디버그

기본적으로 디버거 호출 하는 설정을 사용 하 여 앱 코드만 디버그 하려고 *Just My Code*합니다. 다른 프로젝트 형식 및 언어에 대해이 기능을 작동 하는 방법 및 방법을 사용자 지정할 수 있습니다 하는 방법에 대 한 자세한 내용은 참조 하세요. [Just My Code](../debugger/just-my-code.md)합니다.

검색할 프레임 워크 코드, 타사 라이브러리 코드 또는 시스템 호출에서 디버깅 하는 동안, 내 코드만 비활성화할 수 있습니다. **도구** (또는 **디버그**) > **옵션** > **디버깅**선택을 취소 합니다 **내 코드만** 확인란입니다. 내 코드만 해제 하면 사용자 코드가 아닌 디버거 창에 표시 되며 디버거 비 사용자 코드를 한 단계씩 실행할 수 있습니다.

> [!NOTE]
> 디바이스 프로젝트에 대해서는 내 코드만 옵션이 지원되지 않습니다.

### <a name="debug-system-code"></a>시스템 코드를 디버그 합니다.

Microsoft 시스템 코드에 대 한 디버깅 기호 로드를 내 코드만 사용 하지 않도록 설정 하면, 하는 경우 다른 모든 호출과 경우와 마찬가지로 시스템 호출 한 단계씩 실행할 수 있습니다.

Microsoft 기호를 로드 하려면 참조 [기호 위치를 구성 하 고 로드 옵션](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#configure-symbol-locations-and-loading-options)합니다.

**특정 시스템 구성 요소에 대 한 기호를 로드 합니다.**

1. 디버그 하는 동안 엽니다는 **모듈** 를 선택 하 여 창 **디버그** > **Windows** > **모듈**를 누르거나 **Ctrl**+**Alt**+**U**합니다.

1. 에 **모듈** 창에서 확인할 수 있습니다는 기호가 로드 된 모듈을 합니다 **기호 상태** 열입니다. 선택한 기호를 로드 하려는 모듈을 마우스 오른쪽 단추로 클릭 **기호 로드**합니다.

##  <a name="BKMK_Step_into_properties_and_operators_in_managed_code"></a> 한 단계씩 관리 코드의 속성 및 연산자 실행
 기본적으로 디버거는 관리 코드의 속성과 연산자를 건너뜁니다. 대부분의 경우 이렇게 하면 더 나은 디버깅 환경이 제공됩니다. 속성 또는 연산자를 한 단계씩 실행을 사용 하도록 설정 하려면 **디버깅할** > **옵션**합니다. **디버깅** > **일반** 페이지에서 **속성 및 연산자 건너뛰기(관리 전용)** 확인란의 선택을 취소합니다.

## <a name="see-also"></a>참고 항목
- [디버깅이란?](../debugger/what-is-debugging.md)
- [디버깅 기술 및 도구](../debugger/write-better-code-with-visual-studio.md)
- [디버깅 소개](../debugger/debugger-feature-tour.md)
