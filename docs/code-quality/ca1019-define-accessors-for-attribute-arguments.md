---
title: 'CA1019: 특성 인수의 접근자를 정의하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8a604ea8731108c73c3dfb1c279f2f243c0a05ad
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931182"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: 특성 인수의 접근자를 정의하세요.

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 특성 생성자를 통해 해당 속성이 없는 인수를 정의 합니다.

## <a name="rule-description"></a>규칙 설명
 특성에서는 대상에 특성을 적용할 때 지정해야 하는 필수 인수를 정의할 수 있습니다. 이러한 인수는 특성 생성자에 위치 매개 변수로 제공되기 때문에 이러한 인수를 위치 인수라고도 합니다. 모든 필수 인수에 대해 특성은 실행 시간에 인수의 값을 검색할 수 있도록 해당하는 읽기 전용 속성도 제공해야 합니다. 이 규칙은 각 생성자 매개 변수에 대해 해당 속성 정의 되었는지 확인 합니다.

 특성에서는 명명된 인수라고 하는 선택적 인수도 정의할 수 있습니다. 이들 인수는 이름으로 특성 생성자에 제공되며 해당하는 읽기/쓰기 특성이 있어야 합니다.

 필수 및 선택적 인수, 해당 속성 및 생성자 매개 변수를 사용 해야 하지만 다른 대/소문자 동일한 이름을 지정 합니다. 속성 사용 파스칼식 대/소문자, 및 매개 변수 사용 카멜식 대/소문자입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 없는 각 생성자 매개 변수에 대해 읽기 전용 속성을 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 필수 인수를 검색 가능은 원하지 않는 경우이 규칙에서 경고를 표시 합니다.

## <a name="custom-attributes-example"></a>사용자 지정 특성 예제

다음 예제에서는 필수 (위치) 매개 변수를 정의 하는 두 가지 특성을 보여 줍니다. 특성의 첫 번째 구현 잘못 정의 되었습니다. 두 번째 구현은 올바른 합니다.

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>위치 인수와 명명 된 인수

위치 인수와 명명 된 인수는 인수는 특성에 대 한 필수 인수는 선택 사항 및 라이브러리의 소비자에 게 clear 있도록 합니다.

다음 예제에서는 위치 인수와 명명 된 인수가 있는 특성의 구현을 보여 줍니다.

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

다음 예제에서는 두 개의 속성에 사용자 지정 특성을 적용 하는 방법을 보여 줍니다.

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1813: 봉인 되지 않은 특성](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>참고자료
 [특성](/dotnet/standard/design-guidelines/attributes)