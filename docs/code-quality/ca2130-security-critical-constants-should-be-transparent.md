---
title: 'CA2130: 보안에 중요한 상수는 투명해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a33b650570981f5496813f575b1ae2413a960026
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920768"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: 보안에 중요한 상수는 투명해야 합니다.

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
상수 필드 또는 열거형 멤버는로 <xref:System.Security.SecurityCriticalAttribute>표시 됩니다.

## <a name="rule-description"></a>규칙 설명
런타임에 조회가 필요하지 않도록 컴파일러에서 상수 값을 인라인하기 때문에 상수 값에 투명성이 적용되지 않습니다. 상수 필드는 보안 투명해야 하므로 코드 검토자는 투명 코드가 상수에 액세스할 수 없다고 가정하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 필드 또는 값에서 SecurityCritical 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서 열거형 값 `EnumWithCriticalValues.CriticalEnumValue` 과 상수 `CriticalConstant` 는이 경고를 발생 시킵니다. 문제를 해결 하려면 [`SecurityCritical`] 특성을 제거 하 여 보안을 투명 하 게 만듭니다.

[!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]