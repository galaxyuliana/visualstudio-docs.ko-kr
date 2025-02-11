---
title: 주석 적용 시기 및 위치 지정
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Group_
- _At_
- _When_
- _At_buffer_
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 6c7adb310db9eece1d8d4a2881057cc1acde1062
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923810"
---
# <a name="specifying-when-and-where-an-annotation-applies"></a>주석 적용 시기 및 위치 지정
주석이 조건부 인 경우 분석기에 지정 하기 위해 다른 주석이 필요할 수 있습니다.  예를 들어 함수에 동기 또는 비동기가 될 수 있는 변수가 있으면 함수는 다음과 같이 동작 합니다. 동기 경우에는 항상 성공 하지만 비동기 사례에서는 즉시 성공할 수 없는 경우 오류를 보고 합니다. 함수가 동기적으로 호출 되는 경우 결과 값은 반환 되지 않기 때문에 코드 분석기에 값을 제공 하지 않습니다.  그러나 함수를 비동기적으로 호출 하 고 함수 결과를 확인 하지 않으면 심각한 오류가 발생할 수 있습니다. 이 예에서는이 문서의 뒷부분에서 설명 하는 `_When_` 주석을 사용 하 여 검사를 사용 하는 상황을 보여 줍니다.

## <a name="structural-annotations"></a>구조적 주석
주석이 적용 되는 시기와 위치를 제어 하려면 다음 구조 주석을 사용 합니다.

|Annotation|Description|
|----------------|-----------------|
|`_At_(expr, anno-list)`|`expr`lvalue를 생성 하는 식입니다. 의 주석은에 `anno-list` 의해 `expr`이름이 지정 된 개체에 적용 됩니다. 의 `anno-list`각 주석에 대해는 `expr` 사전 조건에서 주석이 해석 되는 경우 사전 조건으로 해석 되 고, 주석이 사후 조건에서 해석 되는 경우 사후 조건으로 해석 됩니다.|
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr`lvalue를 생성 하는 식입니다. 의 주석은에 `anno-list` 의해 `expr`이름이 지정 된 개체에 적용 됩니다. 의 `anno-list`각 주석에 대해는 `expr` 사전 조건에서 주석이 해석 되는 경우 사전 조건으로 해석 되 고, 주석이 사후 조건에서 해석 되는 경우 사후 조건으로 해석 됩니다.<br /><br /> `iter`주석으로 범위가 지정 된 변수 이름입니다 (포함 `anno-list`). `iter`에는 암시적 형식이 `long`있습니다. 모든 바깥쪽 범위에서 이름이 같은 변수가 계산에서 숨겨집니다.<br /><br /> `elem-count`정수로 계산 되는 식입니다.|
|`_Group_(anno-list)`|의 `anno-list` 주석은 모두 각 주석에 적용 되는 그룹 주석에 적용 되는 한정자를 포함 하는 것으로 간주 됩니다.|
|`_When_(expr, anno-list)`|`expr`로 `bool`변환할 수 있는 식입니다. 0이 아닌 경우 (`true`)에 `anno-list` 지정 된 주석은 해당 하는 것으로 간주 됩니다.<br /><br /> 기본적으로의 `anno-list`각 주석은 주석이 사전 조건이 `expr` 면 입력 값을 사용 하는 것으로 해석 되 고, 주석이 사후 조건인 경우에는 출력 값을 사용 하는 것으로 해석 됩니다. 기본값을 재정의 하려면 입력 값을 사용 해야 `_Old_` 함을 나타내기 위해 사후 조건을 평가할 때 내장 함수를 사용할 수 있습니다. **참고:**  사전 조건 `expr` 에서 계산 된 결과가 사후 조건에서 계산 `_When_` 된 결과와 다를 수 있기 때문 `*pLength`에 변경 가능한 값 (예:)이 포함 된 경우를 사용 하 여 다른 주석을 사용 하도록 설정할 수 있습니다.|

## <a name="see-also"></a>관련 항목

- [C/C++ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL 이해](../code-quality/understanding-sal.md)
- [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)
- [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)
- [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)
- [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)
- [내장 함수](../code-quality/intrinsic-functions.md)
- [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)