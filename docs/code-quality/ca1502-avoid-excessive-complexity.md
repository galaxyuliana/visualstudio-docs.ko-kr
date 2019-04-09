---
title: 'CA1502: 지나치게 복잡하게 만들지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e968cef6491e1c24d98e5f64248b5104db8c5b65
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232318"
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: 지나치게 복잡하게 만들지 마세요.

|||
|-|-|
|TypeName|AvoidExcessiveComplexity|
|CheckId|CA1502|
|범주|Microsoft.Maintainability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

메서드는 과도 한 순환 복잡성을 있습니다.

## <a name="rule-description"></a>규칙 설명

*순환 복잡성* 수와 조건부 분기의 복잡성에 따라 결정 되는 메서드를 통해 선형 독립 경로의 수를 측정 합니다. 일반적으로 낮은 순환 복잡성을 이해 하 고, 테스트 및 유지 관리 하기 쉬운 메서드를 나타냅니다. 순환 복잡성 메서드의 제어 흐름 그래프에서 계산 되 고 다음과 같이 지정 됩니다.

순환 복잡성 = 노드의 수 + 1-에 지 수

A *노드* 논리 분기 지점을 나타내는 *edge* 노드 사이 선을 나타냅니다.

순환 복잡성 25 개가 넘는 경우 규칙 위반을 보고 합니다.

코드 메트릭에 대 한 자세히 알아볼 수 있습니다 [관리 되는 코드의 복잡성을 측정](../code-quality/code-metrics-values.md)합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 순환 복잡성을 줄이기 위해 메서드를 리팩터링 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

복잡성을 쉽게 줄일 수 없고 및 메서드 이해, 테스트 및 유지 관리 하기 쉽습니다.이 규칙에서 경고 표시 하지 않아도 안전 합니다. 특히 많이 포함 된 메서드 `switch` (`Select` 에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 문을 제외에 대 한 후보입니다. 기본 개발 주기 또는 런타임 동작 이전에 제공 된 코드에서 예기치 않게 변경의 지연 될 수 있습니다 유지 관리의 이점을 능가 하는 코드를 리팩터링 하는 코드를 불안정의 위험이 있습니다.

## <a name="how-cyclomatic-complexity-is-calculated"></a>순환 복잡성 계산 되는 방법

순환 복잡성 다음과 1을 더하여 계산 됩니다.

- 분기 수 (같은 `if`, `while`, 및 `do`)

- 수가 `case` 문에서 `switch`

## <a name="example"></a>예제

다음 예제에서는 다양 한 순환 복잡성을 가진 메서드를 보여 줍니다.

**1의 순환 복잡성**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]

## <a name="example"></a>예제

**2의 순환 복잡성**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]

## <a name="example"></a>예제

**3의 순환 복잡성**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]

## <a name="example"></a>예제

**8의 순환 복잡성**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]

## <a name="related-rules"></a>관련된 규칙

[CA1501: 상속성을 너무 많이 사용하지 마세요.](../code-quality/ca1501-avoid-excessive-inheritance.md)

## <a name="see-also"></a>참고자료

- [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/code-metrics-values.md)