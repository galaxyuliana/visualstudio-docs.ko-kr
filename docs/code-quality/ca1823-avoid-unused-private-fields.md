---
title: 'CA1823: 사용되지 않는 전용 필드를 사용하지 마세요.'
ms.date: 11/04/2016
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
ms.openlocfilehash: 47a2ad3b64055584551a63a2333e29286783d8cf
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921354"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: 사용되지 않는 전용 필드를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidUnusedPrivateFields|
|CheckId|CA1823|
|범주|Microsoft.Performance|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
이 규칙은 코드의 전용 필드가 있지만 코드 경로에서 사용 되지 않을 때 보고 됩니다.

## <a name="rule-description"></a>규칙 설명
어셈블리에서 액세스되지 않는 것으로 보이는 전용 필드가 발견되었습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 필드를 제거 하거나 필드를 사용 하는 코드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="related-rules"></a>관련 규칙
[CA1812: 인스턴스화되지 않은 내부 클래스를 사용 하지 마십시오.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1801: 사용 하지 않는 매개 변수 검토](../code-quality/ca1801-review-unused-parameters.md)

[CA1804: 사용 하지 않는 지역 제거](../code-quality/ca1804-remove-unused-locals.md)

[CA1811: 호출 되지 않는 private 코드 방지](../code-quality/ca1811-avoid-uncalled-private-code.md)