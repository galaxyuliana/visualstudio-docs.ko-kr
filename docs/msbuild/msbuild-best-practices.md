---
title: MSBuild 모범 사례 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae4390632dc9c1ce0cb47d5733145739719ae87c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617355"
---
# <a name="msbuild-best-practices"></a>MSBuild 모범 사례
MSBuild 스크립트를 작성할 때는 다음 모범 사례를 따르는 것이 좋습니다.

-   기본 속성 값은 명령줄에서 기본값을 재정의할 수 있는 속성을 선언하는 대신 `Condition` 특성을 사용하여 처리하는 것이 가장 효율적입니다. 예를 들어 다음과 같은 코드를 사용합니다.

```xml
<MyProperty Condition="'$(MyProperty)' == ''">
   MyDefaultValue
</MyProperty>
```

-   항목을 선택할 때는 와일드카드를 사용하지 않습니다. 대신 파일을 명시적으로 지정합니다. 이렇게 하면 파일을 추가하거나 삭제할 때 발생할 수 있는 오류를 보다 쉽게 추적할 수 있습니다.

## <a name="see-also"></a>참고 항목
- [고급 개념](../msbuild/msbuild-advanced-concepts.md)
