---
title: XAML 디자이너에서 개체에 애니메이션 효과 주기
ms.date: 04/11/2018
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: a5bd9c24351201d066f9055554468939df02b33e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62927034"
---
# <a name="animate-objects-in-xaml-designer"></a>XAML 디자이너에서 개체에 애니메이션 효과 주기

개체를 이동하는 간단한 애니메이션을 만들 수 있고 개체를 페이드 인/페이드 아웃할 수 있습니다.

시작하려면 *스토리보드*를 만듭니다. 스토리보드에는 하나 이상의 *타임 라인*이 포함됩니다. 타임라인에서 *키 프레임* 을 설정하여 속성 변경 내용을 표시합니다. 그런 다음 애니메이션을 실행하면 Blend가 지정된 기간 동안 속성 변경 내용을 보간합니다. 따라서 부드러운 전환이 가능해집니다. 비시각적 속성을 비롯하여 개체에 속하는 모든 속성에 애니메이션 효과를 적용할 수 있습니다.

다음 그림은 **위로 이동**이라고 하는 스토리보드를 보여 줍니다. 타임라인에는 사각형의 X 및 Y 위치를 표시하는 키 프레임이 포함됩니다. 이 애니메이션을 실행하면 사각형이 특정 위치에서 다른 위치로 부드럽게 이동합니다.

![XAML 디자이너의 MoveUp 스토리보드](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>참고 항목

- [Blend for Visual Studio를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)