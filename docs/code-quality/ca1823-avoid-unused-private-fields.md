---
title: 'CA1823: 사용되지 않는 전용 필드를 사용하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ad70fbcb8052e45f4819db2f8d423ce4f70ce697
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971535"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: 사용되지 않는 전용 필드를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidUnusedPrivateFields|
|CheckId|CA1823|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 이 규칙은 코드에 전용 필드가 있지만 모든 코드 경로에서 사용 되지 않는 경우 보고 됩니다.

## <a name="rule-description"></a>규칙 설명
 어셈블리에서 액세스되지 않는 것으로 보이는 전용 필드가 발견되었습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 필드를 제거 하거나 사용 하는 코드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1812: 인스턴스화되지 않은 내부 클래스를 방지 합니다.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: 사용 되지 않는 매개 변수를 검토](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: 사용 되지 않는 로컬 항목을 제거](../code-quality/ca1804-remove-unused-locals.md)

 [CA1811: 호출 되지 않는 전용 코드를 방지 합니다.](../code-quality/ca1811-avoid-uncalled-private-code.md)