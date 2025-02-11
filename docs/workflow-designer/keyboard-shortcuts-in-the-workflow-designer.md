---
title: '워크플로 디자이너: 바로 가기 키'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDKeyboardShortcuts.UI
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b2026c61d05425f0f0d48a9fb722c62f760fcba2
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825518"
---
# <a name="keyboard-shortcuts-in-the-workflow-designer"></a>워크플로 디자이너의 바로 가기 키

모든 워크플로 디자이너의 핵심 기능을 바로 가기에서 액세스할 수 있습니다.

## <a name="navigating-the-workflow-designer-using-the-keyboard"></a>키보드를 사용하여 워크플로 디자이너 탐색

Visual Studio 내에서 전역 바로 가기와 디버깅 바로 가기가 워크플로 디자이너에 적용 됩니다. 또한 다양 한 워크플로 디자이너 관련 바로 가기 키를 만들었습니다. Visual Studio에서 모든 바로 가기 키를 다시 매핑할 수 있습니다. 하지만 다시 호스트된 애플리케이션에는 이러한 바로 가기 키가 하드 코딩되어 있습니다.

### <a name="workflow-designer-keyboard-shortcuts"></a>Workflow Designer 바로 가기 키

다음 표에서 워크플로 디자이너 명령에 할당 된 기본 바로 가기 키를 보여 줍니다.

|바로 가기|용도|
|-|-------------|
|Ctrl+E, A|인수 디자이너를 표시하거나 숨깁니다.|
|Ctrl+E, C|현재 위치에서 선택한 활동을 축소합니다.|
|Ctrl+E, E|현재 위치에서 선택한 활동을 확장합니다.|
|Ctrl+E, F|순서도에서 선택한 활동을 연결합니다.|
|Ctrl+E, I|가져오기 디자이너를 표시하거나 숨깁니다.|
|Ctrl+E, M|키보드 포커스를 탭 순서의 다음 항목으로 이동합니다.|
|Ctrl+E, N|선택한 활동(또는 가장 가까운 활동) 범위 내에 새 변수를 만듭니다.|
|Ctrl+E, O|개요 맵을 표시하거나 숨깁니다.|
|Ctrl+E, P|선택한 활동의 부모로 이동합니다. 그러면 이동 경로 탐색에서 한 수준 위로 올라가면서 디자이너 화면의 루트 활동이 바뀝니다.|
|Ctrl+E, S|키보드 포커스가 있는 항목을 현재 선택에 추가합니다.|
|Ctrl+E, V|변수 디자이너를 표시하거나 숨깁니다.|
|Ctrl+E, X|워크플로의 모든 활동을 확장합니다.|
|Ctrl+Alt+F6|키보드 포커스를 현재 UI 영역에서 시퀀스의 다음 영역으로 이동합니다. 순서는 다음과 같습니다.<br /><br /> 1.  이동 경로 탐색 막대<br />2.  디자이너 화면<br />3.  인수/변수/가져오기 디자이너(열려 있는 경우)<br />4.  셸|

### <a name="flowchart"></a>Flowchart

다음 목록은 키보드로 순서도를 구성하는 데 사용되는 제스처를 보여 줍니다. 워크플로 디자이너의 나머지 부분에서와 같이 Visual Studio를 사용 하 여 제공 된 전역 도구 상자 바로 가기를 사용 하 여 디자이너 화면에 활동을 추가 합니다.

- 활동을 이동하려면 활동을 선택하고 화살표 키를 사용하여 활동 위치를 조정합니다.

- 순서도의 크기를 조정하려면 화살표 키를 사용하여 순서도의 현재 경계 너머로 활동을 이동합니다. 순서도의 크기가 자동으로 조정됩니다.

- 작업을 시작 노드로 설정 하려면 합니다 **노드로 설정** 오른쪽 클릭 메뉴에서 명령을 합니다.

- 활동을 연결하려면

    1. 소스 활동으로 이동하여 해당 활동을 선택합니다.

    2. Ctrl+E, M을 여러 번 눌러 키보드 포커스를 대상 활동으로 옮깁니다.

    3. Ctrl+E, S를 눌러 대상 활동을 선택 항목에 추가합니다.

    4. Ctrl+E, F를 눌러 소스의 커넥터를 대상에 추가합니다.

키보드로 활동을 연결하는 방법에 대한 참고 사항은 다음과 같습니다.

- 더 많은 활동을 선택 항목에 추가한 후 Ctrl+E, F를 눌러 여러 연결을 동시에 만들 수 있습니다. 선택 항목에 활동을 추가한 순서로 연결이 이루어집니다.

- 활동 쌍을 연결할 수 없는 경우(예: 소스 활동에 나가는 연결이 이미 있는 경우)에도 가능하면 선택 항목의 활동 사이에 다른 연결이 설정됩니다.

- 경우는 **FlowDecision** 선택 영역에 포함 되어 및 **FlowDecision** 에 나가는 커넥터가 없는 경우 커넥터에 배치 됩니다는 **True** 분기 합니다.

### <a name="expression-editing"></a>식 편집

기본적으로 Visual Basic 텍스트 편집에 대 한 기본 바로 가기 키 식으로 편집기 내부에서 Workflow Designer에서 다음과 같은 제한 사항이 적용 됩니다.

- 다음 명령에 대한 바로 가기 키를 다시 매핑할 수 없습니다. 식을 편집할 때 이러한 명령에 액세스하기 위해서는 기본 바로 가기 키만 사용할 수 있습니다.

  - 잘라내기
  - 복사
  - 붙여넣기
  - 모두 선택
  - 실행 취소
  - Redo

- Visual Studio에서 워크플로 디자이너 내에서 식 편집 명령에 대 한 바로 가기 키를 다시 매핑할, 워크플로 디자이너 범위에서 바로 가기를 편집 합니다. 텍스트 편집기 범위에서 변경한 내용을 자동으로 워크플로 디자이너에 적용 되지 않습니다. 따라서 양쪽 모두에서 바로 가기를 다시 매핑하려면 범위마다 한 번씩 변경을 두 번 적용해야 합니다.
