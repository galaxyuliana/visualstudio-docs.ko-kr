---
title: 'CA1801: 사용되지 않은 매개 변수를 검토하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidUnusedParameters
- CA1801
- ReviewUnusedParameters
helpviewer_keywords:
- CA1801
- ReviewUnusedParameters
ms.assetid: 5d73545c-e153-4b7c-a7b2-be6bf5aca5be
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dea30f8053844cc6ce6eb38dd5138e935e8020df
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029897"
---
# <a name="ca1801-review-unused-parameters"></a>CA1801: 사용되지 않은 매개 변수를 검토하세요.

|||
|-|-|
|TypeName|ReviewUnusedParameters|
|CheckId|CA1801|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님-멤버를 변경 하면에 관계 없이 어셈블리 외부에서 볼 수 없는 경우.<br /><br /> 주요 변경 아님-본문 내에서 매개 변수를 사용 하 여 멤버를 변경 하는 경우.<br /><br /> 주요-매개 변수를 제거 하 고 어셈블리 외부에 표시 됩니다.|

## <a name="cause"></a>원인
 메서드 시그니처에 메서드 본문에서 사용되지 않는 매개 변수가 있습니다. 이 규칙에서 다음 메서드를 검사 하지 않습니다.

- 참조 하는 대리자 메서드입니다.

- 메서드를 이벤트 처리기로 사용 합니다.

- 사용 하 여 선언 된 메서드를 `abstract` (`MustOverride` Visual basic에서) 한정자.

- 사용 하 여 선언 된 메서드를 `virtual` (`Overridable` Visual basic에서) 한정자.

- 사용 하 여 선언 된 메서드를 `override` (`Overrides` Visual basic에서) 한정자.

- 메서드를 사용 하 여 선언 된 `extern` (`Declare` Visual Basic의 문) 한정자.

## <a name="rule-description"></a>규칙 설명
 메서드 본문에 액세스 하는 데 실패 수정 사항이 있는지 확인 하려면 사용 되지 않는 비가상 메서드의 매개 변수를 검토 합니다. 사용 되지 않는 매개 변수에는 유지 관리 및 성능 비용이 발생합니다.

 경우에 따라이 규칙 위반 메서드 구현 버그를 가리킬 수 있습니다. 예를 들어, 매개 변수에 메서드 본문에서 사용 된 해야 합니다. 해당 매개 변수가 이전 버전과 호환성 때문에 존재 하는 경우에이 규칙의 경고를 표시 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 사용 되지 않는 매개 변수 (주요 변경 내용)를 제거 하거나 메서드 본문 (줄 바꿈하지 않는 변경)의 매개 변수를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이전에 제공 된 코드는 수정 프로그램은 주요 변경 내용에 대 한이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 두 가지 방법을 보여 줍니다. 한 가지 방법은 해당 규칙을 위반 하 고 규칙을 충족 하는 다른 메서드.

 [!code-csharp[FxCop.Usage.ReviewUnusedParameters#1](../code-quality/codesnippet/CSharp/ca1801-review-unused-parameters_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1811: 호출 되지 않는 전용 코드를 방지 합니다.](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: 인스턴스화되지 않은 내부 클래스를 방지 합니다.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: 사용 되지 않는 로컬 항목을 제거](../code-quality/ca1804-remove-unused-locals.md)