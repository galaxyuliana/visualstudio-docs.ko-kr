---
title: 'CA1309: 서수 StringComparison을 사용하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2c528266c54bbb2f3f0d9420461d700a46b09bd5
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922275"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: 서수 StringComparison을 사용하세요.

|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|범주|Microsoft.Globalization|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

비 언어적 인 문자열 비교 작업은 <xref:System.StringComparison> 매개 변수를 **서 수** 또는 **stringcomparison.ordinalignorecase**로 설정 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
이제 및 <xref:System.String.Compare%2A?displayProperty=fullName> <xref:System.String.Equals%2A?displayProperty=fullName> 메서드는 대부분의 문자열 작업에서 열거형 값을 <xref:System.StringComparison?displayProperty=fullName> 매개 변수로 허용 하는 오버 로드를 제공 합니다.

**StringComparison** 또는 **StringComparison**중 하나를 지정 하는 경우 문자열 비교는 비 언어적입니다. 즉, 자연어와 관련 된 기능은 비교 결정을 내릴 때 무시 됩니다. 자연어 기능을 무시 하는 것은 문화권에 의해 매개 변수화 된 대/소문자 구분 또는 동등 테이블이 아닌 단순 바이트 비교를 기반으로 결정을 내리는 것입니다. 결과적으로 매개 변수를 **StringComparison** 또는 **StringComparison**로 명시적으로 설정 하 여 코드에서 속도가 향상 되 고, 정확성을 높이고, 안정성이 향상 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 문자열 비교 메서드를 <xref:System.StringComparison?displayProperty=fullName> 열거형을 매개 변수로 허용 하는 오버 로드로 변경 하 고 **서 수** 또는 **stringcomparison.ordinalignorecase**를 지정 합니다. 예를 들어, `String.Compare(str1, str2)`를 `String.Compare(str1, str2, StringComparison.Ordinal)`로 변경합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
라이브러리나 응용 프로그램이 제한 된 로컬 대상 사용자를 위한 것 이거나 현재 문화권의 의미 체계를 사용 해야 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="see-also"></a>참고자료

- [전역화 경고](../code-quality/globalization-warnings.md)
- [CA1307: StringComparison 지정](../code-quality/ca1307-specify-stringcomparison.md)