---
title: 'CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ffc94a04d708315cc143afd1556cb8a2f0072e91
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923294"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
외부에 노출 되는 제네릭 형식에는 두 개 이상의 형식 매개 변수가 있습니다.

## <a name="rule-description"></a>규칙 설명
제네릭 형식에 포함된 형식 매개 변수가 많을수록 각 형식 매개 변수가 무엇을 나타내는지를 파악하거나 기억하기가 더 어렵습니다. 일반적으로에서와 같이 하나의 형식 매개 변수 `List<T>`를 사용 하는 경우와 `Dictionary<TKey, TValue>`같이 두 개의 형식 매개 변수를 사용 하는 것이 명확 합니다. 세 개 이상의 형식 매개 변수가 있는 경우 대부분의 사용자에 게 `TooManyTypeParameters<T, K, V>` 어려움 (예: C# 또는 `TooManyTypeParameters(Of T, K, V)` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의)이 너무 유용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 두 개 이상의 형식 매개 변수를 사용 하도록 디자인을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
디자인에서 두 개 이상의 형식 매개 변수를 요구 하지 않는 한이 규칙에서 경고를 표시 하지 마십시오. 쉽게 이해 하 고 사용할 수 있는 구문에서 제네릭을 제공 하면 새 라이브러리의 도입 률을 배우고 늘리는 데 필요한 시간이 단축 됩니다.

## <a name="related-rules"></a>관련 규칙
[CA1010: 컬렉션은 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000: 정적 멤버를 제네릭 형식으로 선언 하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1002: 제네릭 목록을 노출 하지 않습니다.](../code-quality/ca1002-do-not-expose-generic-lists.md)

[CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

[CA1004: 제네릭 메서드는 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

[CA1003: 제네릭 이벤트 처리기 인스턴스 사용](../code-quality/ca1003-use-generic-event-handler-instances.md)

[CA1007: 적절 한 경우 제네릭을 사용 합니다.](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료
[제네릭](/dotnet/csharp/programming-guide/generics/index)