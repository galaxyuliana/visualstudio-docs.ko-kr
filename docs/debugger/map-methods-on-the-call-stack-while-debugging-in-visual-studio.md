---
title: 호출 스택의 시각적 맵 만들기 | Microsoft Docs
ms.date: 11/26/2018
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3de5a3f9e9c5b8f89a9c8917794247098ba12d06
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62846804"
---
# <a name="create-a-visual-map-of-the-call-stack-while-debugging-c-visual-basic-c-javascript"></a>디버깅 하는 동안 호출 스택의 시각적 맵 만들기 (C#, Visual Basic의 경우 C++, JavaScript)

디버깅하는 동안 호출 스택을 시각적으로 추적할 코드 맵을 만듭니다. 맵을 기록해 두면 코드에서 어떤 작업을 하고 있는지 추적하여 버그를 찾는 데 집중할 수 있습니다.

연습에서는이 비디오를 시청 하세요. [비디오: 코드 맵 디버거 통합 (채널 9)를 사용 하 여 시각적으로 디버그](http://go.microsoft.com/fwlink/?LinkId=293418)

명령 및 코드 맵을 사용 하 여 사용할 수 있는 작업의 세부 정보를 참조 하세요 [찾아보기 및 다시 정렬 코드 맵](../modeling/browse-and-rearrange-code-maps.md)합니다.

>[!IMPORTANT]
>만들 수 있습니다 코드 에서만 맵을 [Visual Studio Enterprise edition](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)합니다.

코드 맵 개요는 다음과 같습니다.

 ![코드 맵의 호출 스택으로 디버그](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")

## <a name="MapStack"></a> 호출 스택 매핑

1. Visual Studio Enterprise에서 C#, Visual Basic의 경우 C++, 또는 JavaScript 프로젝트를 선택 하 여 디버깅을 시작할 **디버그** > **디버깅 시작** 키를 누르거나 **F5** .

1. 앱 중단 모드로 들어가거나 한 함수 한 단계씩 실행, 한 후 선택 **디버그** > **코드 맵**를 누르거나 **Ctrl**+**Shift** +**`**.

   현재 호출 스택은 새 코드 맵에 주황색으로 표시됩니다.

   ![참조 코드 맵에 호출 스택](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

코드 디버깅을 계속할 때 업데이트를 자동으로 매핑합니다. 맵 항목 또는 레이아웃 변경 코드에 전혀 영향을 주지 않습니다. 맵에서 이름 바꾸기, 이동 또는 제거 기능을 자유롭게 사용할 수 있습니다.

항목에 대 한 자세한 정보를 가져오려면 위로 마우스를 항목의 도구 설명을 확인 합니다. 선택할 수도 있습니다 **범례** 도구 모음의 각 아이콘의 의미에 대해 알아봅니다.

![지도 범례의 코드](../debugger/media/debuggermap_showlegend.png "지도 범례의 코드")

>[!NOTE]
>메시지 **다이어그램을 기반 하 여 코드의 이전 버전으로 있습니다** 맵 코드의 맨 위에 있는 지도 마지막으로 업데이트 한 후 코드가 변경 될 수 있습니다는 의미 합니다. 예를 들어 맵에 대한 호출이 더 이상 코드에 없는 경우가 있습니다. 메시지를 닫은 다음 맵을 다시 업데이트하기 전에 솔루션 다시 빌드를 시도합니다.

## <a name="map-external-code"></a>외부 코드 맵

기본적으로 맵에는 고유한 코드만 나타납니다. 맵에서 외부 코드를 보려면:

- 마우스 오른쪽 단추로 클릭 합니다 **호출 스택** 창과 선택 **외부 코드 포시**:

  ![호출 스택 창을 사용 하 여 외부 코드 표시](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")
- 또는 선택 취소 **내 코드만** Visual Studio에서 **도구** (또는 **디버그**) > **옵션**  >   **디버깅**:

  ![옵션 대화 상자를 사용 하 여 외부 코드 표시](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")

## <a name="control-the-maps-layout"></a>맵 레이아웃을 제어 합니다.

맵 레이아웃 변경 코드에 전혀 영향을 주지 않습니다.

맵 레이아웃을 제어 하려면 선택 합니다 **레이아웃** 맵 도구 모음의 메뉴입니다.

에 **레이아웃** 메뉴에서 할 수 있습니다.

- 기본 레이아웃을 변경합니다.
- 선택 취소 하 여 지도 자동으로 다시 정렬 중지 **디버깅 시 자동으로 레이아웃**합니다.
- 선택 취소 하 여 항목을 추가할 때 최소한으로 맵을 다시 정렬 **증분 레이아웃**합니다.

## <a name="MakeNotes"></a> 코드에 대해 메모하기

코드에서 발생 하는 추적 하기 위한 주석을 추가할 수 있습니다.

주석을 추가할 코드 맵을 마우스 오른쪽 단추로 클릭 하 고 선택 **편집할** > **새 주석**, 메모를 입력 합니다.

주석에 새 줄을 추가 하려면 다음을 누릅니다 **Shift**+**Enter**합니다.

 ![코드 맵의 호출 스택에 설명 추가](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")

## <a name="UpdateMap"></a> 다음 호출 스택과 함께 맵 업데이트

함수에 다음 중단점까지 또는 단계 앱을 실행 하면 맵에 새 호출 스택이 자동으로 추가 합니다.

![다음 호출 스택으로 코드 맵 업데이트](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")

맵에 새 호출 스택이 자동으로 추가 중지 하려면 선택 ![자동으로 코드 맵에 표시 호출 스택](../debugger/media/debuggermap_automaticupdateicon.gif "자동으로 코드 맵에 표시 호출 스택") 코드 맵 도구 모음에서 합니다. 맵에 계속 기존 호출 스택을 강조 표시 합니다. 현재 호출 스택을 맵에 수동으로 추가 하려면 다음을 누릅니다 **Ctrl**+**Shift**+**`** 합니다.

## <a name="AddRelatedCode"></a> 맵에 관련 코드 추가

이제를 가져온 후 지도 C# 또는 Visual Basic의 경우 필드, 속성 및 코드에서 발생 하는 추적에 다른 메서드와 같은 항목을 추가할 수 있습니다.

코드에서 메서드 정의로 이동할 맵에서 메서드를 두 번 클릭 하거나 선택 하 고 키를 눌러 **F12**, 또는 마우스 오른쪽 단추로 클릭 하 고 선택 **정의로 이동**합니다.

![코드 맵의 메서드에 대 한 코드 정의로 이동](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

지도에 추적 하려는 항목을 추가 하는 메서드를 마우스 오른쪽 단추로 클릭 하 고 추적 하려는 항목을 선택 합니다. 가장 최근 추가된 항목은 녹색으로 표시됩니다.

![호출 스택 코드 맵의 메서드에 관련 필드](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")

>[!NOTE]
>기본적으로 맵에 항목을 추가하면 클래스, 네임스페이스 및 어셈블리와 같은 부모 그룹 노드도 추가됩니다. 선택 하 여이 기능을 켜고 끌 수 있습니다는 **부모 포함** 코드 맵 도구 모음에서 단추를 눌러 **Ctrl** 항목을 추가 합니다.

![호출 스택 코드 맵의 메서드에서 필드 표시](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")

더 많은 코드를 보려면 맵 빌드를 계속합니다.

 ![필드를 사용 하는 메서드 표시: 호출 스택 코드 맵의](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")

 ![호출 스택 코드 맵의 필드를 사용 하는 방법](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")

## <a name="FindBugs"></a> 맵을 사용하여 버그 찾기
 코드를 시각화하면 버그를 더 빠르게 찾을 수 있습니다. 예를 들어 드로잉 응용 프로그램에서 버그를 조사 한다고 가정 합니다. 선을 그렸다가 취소하려는 경우 다른 선을 그릴 때까지 아무 것도 발생하지 않습니다.

 따라서 `clear`, `undo` 및 `Repaint` 메서드에서 중단점을 설정하고, 디버깅을 시작하고, 다음과 같은 맵을 빌드합니다.

 ![다른 호출 스택 코드 맵에 추가](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 `Repaint`를 제외하고 맵 호출 `undo`에 대한 모든 사용자 제스처를 확인할 수 있습니다. `undo`가 즉시 작동하지 않는 이유를 이해할 수 있을 것입니다.

 맵에 새 호출에서 추가 버그를 수정 하 고 계속 앱을 실행 한 후 `undo` 에 `Repaint`:

 ![새 메서드 호출 스택 코드 맵에 추가](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

## <a name="share-the-map-with-others"></a>다른 사용자와 맵 공유

맵 내보내기 Microsoft Outlook을 사용 하 여 다른 사용자에 게 전송 및 솔루션에 저장 버전 제어에 체크 인할 수 있습니다.

를 공유 하거나 맵을 저장 **공유** 코드 맵 도구 모음에 있습니다.

![다른 사용자와 공유 호출 스택 코드 맵의](../debugger/media/debuggermap_sharewithothers.png "다른 사용자와 공유 호출 스택 코드 맵")

## <a name="see-also"></a>참고자료
[솔루션 전체의 종속성 매핑](../modeling/map-dependencies-across-your-solutions.md)

[코드 맵을 사용하여 응용 프로그램 디버그](../modeling/use-code-maps-to-debug-your-applications.md)

[코드 맵 분석기를 사용하여 잠재적 문제 찾기](../modeling/find-potential-problems-using-code-map-analyzers.md)

[코드 맵 찾아보기 및 다시 정렬](../modeling/browse-and-rearrange-code-maps.md)
