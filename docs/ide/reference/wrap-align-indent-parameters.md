---
title: 래핑, 들여쓰기, 매개 변수 정렬
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 1490ff0bcae91a6f4870b0cfb623d975fa1e064b
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335888"
---
# <a name="wrap-indent-and-align-parameters"></a>래핑, 들여쓰기 및 매개 변수 정렬

이 리팩터링은 다음에 적용됩니다.

- C#

- Visual Basic

**내용:** 매개 변수를 래핑, 들여쓰기 및 정렬할 수 있습니다.

**시기:** 여러 개의 매개 변수가 있는 메서드 선언 또는 호출이 있습니다.

**이유:** 사용자 기본 설정에 따라 래핑하거나 들여쓰기할 때 긴 매개 변수의 목록을 읽는 것이 더 쉽습니다.

## <a name="how-to"></a>방법

1. 매개 변수 목록에 커서를 놓습니다.
2. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.

   ![래핑, 들여쓰기 및 매개 변수 정렬](media/wrap-parameters.png)

3. **Enter**를 눌러 리팩터링을 수락합니다.

   ![래핑, 들여쓰기 및 적용되는 매개 변수 정렬](media/wrap-parameters-completed.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
