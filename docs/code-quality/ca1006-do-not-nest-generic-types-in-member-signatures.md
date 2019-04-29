---
title: 'CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotNestGenericTypesInMemberSignatures
- CA1006
helpviewer_keywords:
- CA1006
- DoNotNestGenericTypesInMemberSignatures
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 72d75985482ebf7e90db9d817212882b5ed8c292
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779641"
---
# <a name="ca1006-do-not-nest-generic-types-in-member-signatures"></a>CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마세요.

|||
|-|-|
|TypeName|DoNotNestGenericTypesInMemberSignatures|
|CheckId|CA1006|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 멤버 중첩된 된 형식 인수가 포함 된 시그니처가 있습니다.

## <a name="rule-description"></a>규칙 설명
 중첩된 형식 인수는 제네릭 형식의 인수입니다. 시그니처에 중첩된 형식 인수가 포함되어 있는 멤버를 호출하려면 제네릭 형식 하나를 인스턴스화하고 이 형식을 두 번째 제네릭 형식의 생성자에 전달해야 합니다. 이 경우 복잡한 프로시저와 구문이 필요하므로 이 방법을 피해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 중첩 된 형식 인수를 제거 하려면 디자인을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 새 라이브러리의 도입 률을 높이고 학습에 걸리는 시간이 줄어듭니다 제네릭을 이해 및 사용 하기 쉬운 구문 제공 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 메서드 및 위반 메서드를 호출 하는 데 필요한 구문을 보여 줍니다.

 [!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
 [!code-csharp[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1005: 제네릭 형식에 매개 변수를 방지 합니다.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: 컬렉션에서 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: 제네릭 형식에 정적 멤버를 선언 하지 마십시오](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: 제네릭 목록을 노출 하지 마십시오](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1004: 제네릭 메서드 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용 합니다.](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: 적합 한 제네릭을 사용합니다](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료
 [제네릭](/dotnet/csharp/programming-guide/generics/index)