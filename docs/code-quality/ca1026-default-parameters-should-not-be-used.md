---
title: 'CA1026: 기본 매개 변수를 사용하면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 888e1b5d551e357eb732dfe3f7661d51cbdf089d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923135"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: 기본 매개 변수를 사용하면 안 됩니다.

|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
외부에 노출 되는 형식에는 기본 매개 변수를 사용 하는 외부적으로 표시 되는 메서드가 포함 됩니다.

## <a name="rule-description"></a>규칙 설명
기본 매개 변수를 사용 하는 메서드는 CLS (공용 언어 사양)에서 허용 됩니다. 그러나 CLS를 사용 하면 컴파일러에서 이러한 매개 변수에 할당 된 값을 무시할 수 있습니다. 기본 매개 변수 값을 무시 하는 컴파일러에 대해 작성 된 코드는 각 기본 매개 변수에 대 한 인수를 명시적으로 제공 해야 합니다. 프로그래밍 언어에서 원하는 동작을 유지 하려면 기본 매개 변수를 사용 하는 메서드를 기본 매개 변수를 제공 하는 메서드 오버 로드로 바꾸어야 합니다.

컴파일러는 관리 코드에 액세스할 때에 대 한 C++ 관리 되는 확장의 기본 매개 변수 값을 무시 합니다. Visual Basic 컴파일러는 [선택적](/dotnet/visual-basic/language-reference/modifiers/optional) 키워드를 사용 하는 기본 매개 변수가 있는 메서드를 지원 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 기본 매개 변수를 사용 하는 메서드를 기본 매개 변수를 제공 하는 메서드 오버 로드로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 기본 매개 변수와 동등한 기능을 제공 하는 오버 로드 된 메서드를 사용 하는 메서드를 보여 줍니다.

[!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA1025: 반복 인수를 params 배열로 바꾸기](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>참고자료
[언어 독립성 및 언어 독립적 구성 요소](/dotnet/standard/language-independence-and-language-independent-components)