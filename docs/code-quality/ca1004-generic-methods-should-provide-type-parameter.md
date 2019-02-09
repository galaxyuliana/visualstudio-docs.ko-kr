---
title: 'CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 94c21a81a7473e1697609ff3e46eb054ad304540
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955364"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.

|||
|-|-|
|TypeName|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에 표시 되는 제네릭 메서드의 매개 변수 시그니처에 메서드의 형식 매개 변수에 해당 하는 형식이 없습니다.

## <a name="rule-description"></a>규칙 설명
 제네릭 메서드의 형식 인수가 형식 인수를 명시적으로 지정하는 대신 메서드로 전달된 인수의 형식에 따라 결정되는 방식을 유추라고 합니다. 유추를 사용하려면 제네릭 메서드의 매개 변수 시그니처에 메서드에 대한 형식 매개 변수와 같은 형식의 매개 변수가 포함되어야 합니다. 이 경우 형식 인수는 지정할 필요가 없습니다. 모든 형식 매개 변수에 대해 유추를 사용 하는 경우 제네릭 및 제네릭이 아닌 인스턴스 메서드를 호출 하는 구문은 동일 합니다. 이 제네릭 메서드 사용 편의성을 간소화합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드의 각 형식 매개 변수에 대해 동일한 형식 매개 변수 시그니처에 포함 되도록 디자인을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 새 라이브러리의 도입 률을 높이고 학습에 걸리는 시간이 줄어듭니다 제네릭을 이해 및 사용 하기 쉬운 구문 제공 합니다.

## <a name="example"></a>예제
 다음 예제에서는 두 개의 제네릭 메서드를 호출 하기 위한 구문을 보여 줍니다. 에 대 한 형식 인수 `InferredTypeArgument` 유추 됩니다에 대 한 형식 인수 및 `NotInferredTypeArgument` 명시적으로 지정 해야 합니다.

 [!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
 [!code-csharp[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1005: 제네릭 형식에 매개 변수를 방지 합니다.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: 컬렉션에서 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: 제네릭 형식에 정적 멤버를 선언 하지 마십시오](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: 제네릭 목록을 노출 하지 마십시오](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용 합니다.](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: 적합 한 제네릭을 사용합니다](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료
 [제네릭](/dotnet/csharp/programming-guide/generics/index)