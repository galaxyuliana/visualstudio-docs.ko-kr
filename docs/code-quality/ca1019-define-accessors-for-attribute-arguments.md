---
title: 'CA1019: 특성 인수의 접근자를 정의하세요.'
ms.date: 11/04/2016
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
ms.openlocfilehash: 8422427997db291aa24bc8a8bacfdc59abe35998
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923068"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: 특성 인수의 접근자를 정의하세요.

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
해당 생성자에서 특성은 해당 속성이 없는 인수를 정의 합니다.

## <a name="rule-description"></a>규칙 설명
특성에서는 대상에 특성을 적용할 때 지정해야 하는 필수 인수를 정의할 수 있습니다. 이러한 인수는 특성 생성자에 위치 매개 변수로 제공되기 때문에 이러한 인수를 위치 인수라고도 합니다. 모든 필수 인수에 대해 특성은 실행 시간에 인수의 값을 검색할 수 있도록 해당하는 읽기 전용 속성도 제공해야 합니다. 이 규칙은 각 생성자 매개 변수에 대해 해당 속성을 정의 했는지 확인 합니다.

특성에서는 명명된 인수라고 하는 선택적 인수도 정의할 수 있습니다. 이들 인수는 이름으로 특성 생성자에 제공되며 해당하는 읽기/쓰기 특성이 있어야 합니다.

필수 및 선택적 인수의 경우 해당 속성 및 생성자 매개 변수가 동일한 이름을 사용 하지만 대/소문자를 다르게 지정 해야 합니다. 속성은 파스칼식 대/소문자를 사용 하며 매개 변수는 카멜식 대/소문자를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 각 생성자 매개 변수에 대 한 읽기 전용 속성을 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
필수 인수의 값을 검색할 수 없도록 하려면이 규칙에서 경고를 표시 하지 않습니다.

## <a name="custom-attributes-example"></a>사용자 지정 특성 예제

다음 예에서는 필수 (위치) 매개 변수를 정의 하는 두 가지 특성을 보여 줍니다. 특성의 첫 번째 구현이 잘못 정의 되었습니다. 두 번째 구현이 올바릅니다.

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>위치 및 명명 된 인수

위치 및 명명 된 인수를 사용 하면 라이브러리의 소비자가 특성에 필수적인 인수 및 선택적 인수를 명확 하 게 알 수 있습니다.

다음 예제에서는 위치 인수와 명명 된 인수를 모두 포함 하는 특성의 구현을 보여 줍니다.

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

다음 예제에서는 사용자 지정 특성을 두 개의 속성에 적용 하는 방법을 보여 줍니다.

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>관련 규칙
[CA1813: 봉인 되지 않은 특성 방지](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>참고자료
[특성](/dotnet/standard/design-guidelines/attributes)