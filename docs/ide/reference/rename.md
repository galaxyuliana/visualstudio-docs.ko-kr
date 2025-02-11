---
title: 리팩터링 이름 바꾸기
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 2b18f5763d68487e7642f5632c05516d2f1bd9e2
ms.sourcegitcommit: aeb1a1135dd789551e15aa5124099a5fe3f0f32b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66500946"
---
# <a name="rename-a-code-symbol-refactoring"></a>코드 기호 이름 바꾸기 래픽터링

이 리팩터링은 다음에 적용됩니다.

- C#

- Visual Basic

**내용:** 필드, 지역 변수, 메서드, 네임스페이스, 속성 및 형식과 같은 코드 기호의 식별자 이름을 바꿀 수 있습니다.

**시기:** 모든 인스턴스를 찾지 않고도 안전하게 이름을 바꾸고 새 이름을 복사하여 붙여넣으려고 합니다.

**이유:** 전체 프로젝트에 새 이름을 복사하여 붙여넣으면 오류가 발생할 수 있습니다. 이 리팩터링 도구는 이름 바꾸기 작업을 정확하게 수행합니다.

## <a name="how-to"></a>방법

1. 이름을 바꿀 항목을 강조 표시하거나 항목 내부에 텍스트 커서를 놓습니다.

   - C#:

       ![강조 표시된 코드 - C#](media/rename-highlight-cs.png)

   - Visual Basic:

       ![강조 표시된 코드 - Visual Basic](media/rename-highlight-vb.png)

2. 다음 작업 중 하나를 수행합니다.

   - **키보드**
      - **Ctrl+R**을 누른 다음 **Ctrl+R**을 누릅니다. 바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
   - **마우스**
      - **편집 > 리팩터링 > 이름 바꾸기**를 선택합니다.
      - 코드를 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 선택합니다.

3. 항목의 이름을 바꾸려면 새 이름을 입력하면 됩니다.

   - C#:

      ![애니메이션 이름 바꾸기 - C#](media/rename-animated-cs.gif)

   - Visual Basic:

      ![이름 바꾸기 - VB](media/rename-rename-vb.png)

   > [!TIP]
   > 또한 이 새 이름을 사용하도록 주석과 기타 문자열을 업데이트할 뿐만 아니라, 편집기의 오른쪽 위에 표시되는 **이름 바꾸기** 상자의 확인란을 사용하여 저장하기 전에 [변경 내용을 미리 볼](../../ide/preview-changes.md) 수도 있습니다.

4. 변경 내용에 만족할 경우 **적용** 단추를 선택하거나 **Enter** 키를 누르면 변경 내용이 커밋됩니다.

## <a name="remarks"></a>주의

- 충돌을 일으키는 기존 이름을 사용할 경우 **이름 바꾸기** 상자에 경고가 표시됩니다.

   ![이름 바꾸기 충돌](media/rename-conflict-cs.png)

- 기호의 이름을 바꾸는 다른 방법은 편집기에서 해당 이름을 변경하는 것입니다. 그런 다음 커서를 기호 이름에 놓고 **Ctrl**+**을 누릅니다.** 또는 나타나는 전구 아이콘 메뉴를 확장한 후 **이름 바꾸기\<를 선택하여 이전 이름을 \<새 이름**으로 바꿉니다.

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [변경 내용 미리 보기](../../ide/preview-changes.md)
