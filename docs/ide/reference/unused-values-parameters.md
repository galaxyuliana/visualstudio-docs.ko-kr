---
title: 사용되지 않는 값 및 매개 변수
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 1ea80887fff6dcb1afba80feb782b23d1e790579
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325028"
---
# <a name="unused-expression-values-and-parameters"></a>사용되지 않는 식 값 및 매개 변수

이 리팩터링은 다음에 적용됩니다.

- C#
- Visual Basic

**내용:** 사용되지 않는 매개 변수를 페이드 아웃하고 사용하지 않는 식 값에 대한 경고를 생성합니다.

**시기:** 사용되지 않는 매개 변수 또는 식 값이 있습니다.

**이유:** 값 또는 매개 변수가 더 이상 사용되지 않는지 구별하기 어려운 경우가 있습니다. 이러한 값을 페이딩 아웃하거나 경고를 제공하여 삭제할 수 있는 코드를 시각적으로 알 수 있습니다.

## <a name="unused-expression-values-and-parameters-diagnostic"></a>사용되지 않는 식 값 및 매개 변수 진단

1. 사용되지 않는 식 값 또는 매개 변수를 가지고 있습니다.
2. 사용되지 않는 매개 변수가 희미하게 나타납니다. 사용되지 않는 식 값은 경고를 받습니다.

  ![사용되지 않는 매개 변수](media/unused-parameter.png)
  ![사용되지 않는 값](media/unused-value.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [.NET 개발자를 위한 팁](../../ide/visual-studio-2017-for-dotnet-developers.md)
