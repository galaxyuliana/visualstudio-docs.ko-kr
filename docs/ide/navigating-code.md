---
title: 코드 탐색 명령
ms.date: 08/14/2018
ms.topic: conceptual
helpviewer_keywords:
- code editor, navigation
- code editor, go to
- code editor, go to definition
- code editor, go to line
- code editor, peek definition
- code editor, navigation bar
- go to definition
- peek definition
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1263b7a0ae65731eb618ffc925ff0f6310be0f4d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919510"
---
# <a name="navigate-code"></a>코드 탐색

Visual Studio는 편집기에서 코드를 탐색하는 다양한 방법을 제공합니다. 이 항목에서는 코드를 탐색할 수 있는 다른 방법을 간략하게 설명하고, 보다 자세히 설명하는 항목에 대한 링크를 제공합니다.

## <a name="navigate-backward-and-navigate-forward-commands"></a>뒤로 탐색 및 앞으로 탐색 명령

도구 모음에서 **뒤로 탐색**(**Ctrl**+ **-** ) 및 **앞으로 탐색**(**Ctrl**+**Shift**+ **-** ) 버튼을 사용하여 삽입 지점을 이전 위치로 이동하거나 이전 위치에서 최근 위치로 돌아갈 수 있습니다. 이들 단추는 삽입 지점의 마지막 20개 위치를 유지합니다. 이러한 명령은 **보기** 메뉴 아래의 **뒤로 탐색** 및 **앞으로 탐색**에서 사용할 수 있습니다.

![앞으로 및 뒤로 탐색 단추](../ide/media/vs2017_nav_buttons.png)

## <a name="navigation-bar"></a>탐색 모음

**탐색 모음**(코드 창의 맨 위에 있는 드롭다운 상자)을 사용하여 코드베이스에서 코드를 탐색할 수 있습니다. 바로 이동하려면 형식 또는 멤버를 선택합니다. 탐색 모음은 Visual Basic, C# 또는 C++ 코드베이스에서 코드를 편집할 때 나타납니다. 부분 클래스에서 현재 코드 파일 외부에 정의된 멤버는 사용 중지될 수 있습니다(회색으로 표시됨).

![코드 탐색 모음](../ide/media/vside_navigation_bar.png)

다음과 같이 드롭다운 상자에서 탐색할 수 있습니다.

- 현재 파일이 속한 다른 프로젝트로 이동하려면 왼쪽 드롭다운 목록에서 선택합니다.

- 클래스 또는 형식으로 이동하려면 중간 드롭다운에서 선택합니다.

- 클래스의 프로시저 또는 다른 멤버로 직접 이동하려면 오른쪽 드롭다운에서 선택합니다.

- 코드 창에서 탐색 모음으로 포커스를 이동하려면 바로 가기 키 조합 **Ctrl**+**F2** 키를 누릅니다.

- 탐색 모음에서 상자 간에 포커스를 이동하려면 **Tab** 키를 누릅니다.

- 포커스가 지정된 탐색 모음 항목을 선택하고 코드 창으로 돌아가려면 **Enter** 키를 누릅니다.

- 아무 것도 선택하지 않고 탐색 모음에서 코드로 포커스를 돌리려면 **Esc** 키를 누릅니다.

탐색 모음을 숨기려면 **텍스트 편집기 모든 언어** 설정(**도구** > **옵션** > **텍스트 편집기** > **모든 언어**)에서 **탐색 모음** 옵션을 변경하거나, 개별 언어에 대한 설정을 변경할 수 있습니다.

## <a name="find-all-references"></a>모든 참조 찾기

솔루션에서 선택한 요소에 대한 참조를 모두 찾습니다. 이 옵션을 사용하여 큰 리팩터링에서 발생할 수 있는 부작용을 검사하거나 "데드" 코드를 확인할 수 있습니다. 결과 간에 이동하려면 **F8** 키를 누릅니다. 자세한 내용은 [코드에서 참조 찾기](finding-references.md)를 참조하세요.

입력 | 함수
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Shift**+**F12** 키를 누릅니다.
**마우스** | 오른쪽 클릭 메뉴에서 **모든 참조 찾기**를 선택합니다.

## <a name="reference-highlighting"></a>참조 강조 표시

소스 코드에서 기호를 클릭하면 해당 기호의 모든 인스턴스가 문서에서 강조 표시됩니다. 강조 표시된 기호에는 선언 및 참조와 **모든 참조 찾기** 에서 반환하는 다양한 기타 기호가 포함될 수 있습니다. 여기에는 클래스, 개체, 변수, 메서드 및 속성의 이름이 포함됩니다. Visual Basic 코드에서 많은 컨트롤 구조체에 대한 키워드도 강조 표시됩니다. 다음 또는 이전 강조 표시된 기호로 이동하려면 **Ctrl**+**Shift**+**아래쪽 화살표** 또는 **Ctrl**+**Shift**+**위쪽 화살표**를 누릅니다. **도구** > **옵션** > **환경** > **글꼴 및 색** > **강조 표시된 참조**에서 강조 표시 색을 변경할 수 있습니다.

## <a name="go-to-commands"></a>이동 명령

이동에는 **편집** 메뉴의 **이동**에서 사용할 수 있는 다음 명령이 있습니다.

- **줄 이동**(**Ctrl**+**G**): 현재 문서에서 지정된 줄 번호로 이동합니다.

- **전체로 이동**(**Ctrl**+**T** 또는 **Ctrl**+ **,** ): 지정된 줄, 형식, 파일, 멤버 또는 기호로 이동합니다.

- **파일로 이동**(**Ctrl**+**1**, **Ctrl**+**F**): 솔루션에 지정된 파일로 이동합니다.

- **최근에 사용한 파일로 이동**(**Ctrl**+**1**, **Ctrl**+**R**): 솔루션에서 지정되고 최근에 방문한 파일로 이동합니다.

- **형식으로 이동**(**Ctrl**+**1**, **Ctrl**+**T**): 솔루션에 지정된 형식으로 이동합니다.

- **멤버로 이동**(**Ctrl**+**1**, **Ctrl**+**M**): 솔루션에 지정된 멤버로 이동합니다.

- **기호로 이동**(**Ctrl**+**1**, **Ctrl**+**S**): 솔루션에 지정된 기호로 이동합니다.

Visual Studio 2017 버전 15.8 이상에서는 다음과 같은 **이동** 탐색 명령도 사용할 수 있습니다.

- **파일의 다음 문제로 이동**(**Alt**+**PgDn**) 및 **파일의 이전 문제로 이동**(**Alt**+**PgUp**)

- **마지막 편집 위치로 이동**(**Ctrl**+**Shift**+**백스페이스**)

[이동 명령을 사용하여 코드 찾기](../ide/go-to.md) 항목에서 이러한 명령에 대한 자세한 내용을 참조하세요.

## <a name="go-to-definition"></a>정의로 이동

정의로 이동은 선택한 요소의 정의로 이동합니다. 자세한 내용은 [정의로 이동 및 정의 피킹(Peeking)](../ide/go-to-and-peek-definition.md)을 참조하세요.

입력 | 함수
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **F12** 키를 누릅니다.
**마우스** | 형식 이름을 마우스 오른쪽 단추로 클릭하고, **정의로 이동**을 선택하거나 **Ctrl** 키를 누르고, 형식 이름을 클릭합니다.

## <a name="peek-definition"></a>정의 피킹(Peeking)

정의 피킹은 코드 편집기에서 현재 위치를 벗어나지 않고 창에서 선택한 요소의 정의를 표시합니다. 자세한 내용은 [방법: 정의 피킹(Peeking)을 사용하여 코드 보기 및 편집](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) 및 [정의로 이동 및 정의 피킹(Peeking)](../ide/go-to-and-peek-definition.md)을 참조하세요.

입력 | 함수
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Alt**+**F12** 키를 누릅니다.
**마우스** | 형식 이름을 마우스 오른쪽 단추로 클릭하고, **정의 피킹**을 선택하거나 **Ctrl** 키를 누르고, 형식 이름을 클릭합니다(**피크 보기에서 정의 열기** 옵션을 선택한 경우).

## <a name="go-to-implementation"></a>구현으로 이동

구현으로 이동을 사용하여 기본 클래스 또는 형식에서 해당 구현으로 이동할 수 있습니다. 여러 구현이 있는 경우 **기호 찾기 결과** 창에 표시됩니다.

입력 | 함수
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Ctrl**+**F12** 키를 누릅니다.
**마우스** | 형식 이름을 마우스 오른쪽 단추로 클릭하고 **구현으로 이동**을 선택합니다.

## <a name="call-hierarchy"></a>호출 계층 구조

[호출 계층 구조 창](../ide/reference/call-hierarchy.md)에서 메서드에 대한 호출을 볼 수 있습니다.

입력 | 함수
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Ctrl**+**K**, **Ctrl**+**T** 키를 누릅니다.
**마우스** | 멤버 이름을 마우스 오른쪽 단추로 클릭하고 **호출 계층 구조 보기**를 선택합니다.

## <a name="next-method-and-previous-method-commands-visual-basic"></a>다음 메서드 및 이전 메서드와 명령(Visual Basic)

Visual Basic 코드 파일에서 이들 명령을 사용하여 삽입 지점을 다른 메서드로 이동합니다. **편집** > **다음 메서드** 또는 **편집** > **이전 메서드**를 선택합니다.

## <a name="structure-visualizer"></a>구조체 시각화 도우미

코드 편집기의 구조체 시각화 도우미는 코드베이스에서 일치하는 중괄호를 나타내는 *구조체 안내선* - 세로 파선을 표시합니다. 그러면 논리 블록의 시작 및 끝 위치를 보다 쉽게 볼 수 있습니다.

![구조체 시각화 도우미](../ide/media/vside_structure_visualizer.png)

구조체 안내선을 사용하지 않으려면 **도구** > **옵션** > **텍스트 편집기** > **일반**으로 이동하여 **구조체 안내선 표시** 상자의 선택을 취소합니다.

## <a name="enhanced-scroll-bar"></a>향상된 스크롤 막대

코드 창에서 향상된 스크롤 막대를 사용하여 코드의 조감도를 볼 수 있습니다. 맵 모드에서는 커서를 스크롤 막대의 위/아래로 이동할 때 코드 미리 보기를 확인할 수 있습니다. 자세한 내용은 [방법: 스크롤 막대를 사용자 지정하여 코드 추적](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md)을 참조하세요.

## <a name="codelens-information"></a>CodeLens 정보

코드 편집기에서 CodeLens를 사용하면 변경 내용 및 변경한 사용자, 참조, 버그, 작업 항목, 코드 검토, 단위 테스트 상태 같은 특정 코드에 대한 정보를 찾을 수 있습니다. Visual Studio Enterprise를 Team Foundation Server에서 사용할 경우 CodeLens는 화면 표시처럼 작동합니다. [코드 변경 내용 및 기타 기록 찾기](../ide/find-code-changes-and-other-history-with-codelens.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [코드 편집기의 기능](../ide/writing-code-in-the-code-and-text-editor.md)
- [호출 계층 구조 보기](../ide/reference/call-hierarchy.md)
