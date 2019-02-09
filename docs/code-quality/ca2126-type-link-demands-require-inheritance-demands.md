---
title: 'CA2126: 형식 링크 요청에는 상속 요청이 필요합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2fdf92eae202f1ebb80b88e28307e7dacfbc0a39
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55952127"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: 형식 링크 요청에는 상속 요청이 필요합니다.

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 보호 되는 public unsealed 형식이 링크 요청을 사용 하 여 재정의 가능한 메서드가 및 형식이 나 메서드를 모두 상속 요청으로 보호 됩니다.

## <a name="rule-description"></a>규칙 설명
 메서드 또는 해당 선언 형식 링크 요청을 직접 실행 호출자 메서드의 지정 된 권한이 필요 합니다. 메서드에 대 한 상속 요청 재정의 메서드는 지정 된 권한이 필요 합니다. 형식에 대 한 상속 요청 파생 클래스에 지정 된 권한이 필요 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 형식 또는 메서드가 링크 요청으로 동일한 권한에 대 한 상속 요청으로 보호 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2108: 값 형식에서 선언적 보안을 검토 합니다.](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122: 링크 요청이 있는 메서드를 간접적으로 노출 하지 마십시오](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123: 재정의 링크 요청 기본 동일 해야 합니다.](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [링크 요청](/dotnet/framework/misc/link-demands)