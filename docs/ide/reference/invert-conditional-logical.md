---
title: 조건식 및 논리 연산 반전
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 7d59b61cff622a9ba305ebfa86f7c0ebe3c00fe3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62422222"
---
# <a name="invert-conditional-expressions-and-conditional-andor-operators"></a>조건식 및 조건부 AND/OR 연산자 반전

이 리팩터링은 다음에 적용됩니다.

- C#
- Visual Basic

**내용:** 조건식 또는 조건부 AND/OR 연산자를 반전할 수 있습니다.

**시기:** 반전될 경우 더 잘 이해될 수 있는 조건식 또는 조건부 AND/OR 연산자를 가지고 있습니다.

**이유:** 식 또는 조건부 AND/OR 연산자를 수동으로 반전하는 것은 훨씬 더 오래 걸리고 오류가 발생할 수 있습니다. 이 코드 수정은 이 리팩터링을 자동으로 수행할 수 있도록 도와줍니다.

## <a name="invert-conditional-expressions-and-conditional-andor-operators-refactoring"></a>조건식 및 조건부 AND/OR 연산자 리팩터링 반전

1. 커서를 조건식 또는 조건부 AND/OR 연산자에 놓습니다.
2. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.
3. **조건부 반전** 또는 **'&&'를 '||'로 대체** 선택

    ![조건부 반전](media/invert-conditional.png)

    ![조건부 반전](media/invert-logical-operator.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [.NET 개발자를 위한 팁](../../ide/visual-studio-2017-for-dotnet-developers.md)
