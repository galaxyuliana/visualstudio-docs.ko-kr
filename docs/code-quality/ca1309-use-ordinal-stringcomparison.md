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
ms.openlocfilehash: b00accdbdb08e4267bbca2b7e5fab8002f539f1d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922532"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: 서수 StringComparison을 사용하세요.

|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

비언어 문자열 비교 작업을 설정 하지 않습니다 합니다 <xref:System.StringComparison> 매개 변수를 **서** 하거나 **OrdinalIgnoreCase**합니다.

## <a name="rule-description"></a>규칙 설명
 가장 중요 한 점은 많은 문자열 작업에는 <xref:System.String.Compare%2A?displayProperty=fullName> 및 <xref:System.String.Equals%2A?displayProperty=fullName> 메서드를 받아들이는 오버 로드를 이제 제공를 <xref:System.StringComparison?displayProperty=fullName> 열거형 값을 매개 변수로 합니다.

 중 하나를 지정 하는 경우 **StringComparison.Ordinal** 하거나 **StringComparison.OrdinalIgnoreCase**, 비 언어적 문자열 비교 됩니다. 즉, 자연 언어와 관련 된 기능 비교 작업을 결정할 때 무시 됩니다. 자연 언어 기능 무시 하 고 간단한 바이트 비교 및 대/소문자 구분 또는 문화권에 따라 매개 변수화 된 동일 테이블에 없는 결정 기반 의미 합니다. 명시적으로 매개 변수를 설정 하 여 결과적으로 **StringComparison.Ordinal** 또는 **StringComparison.OrdinalIgnoreCase**, 코드 종종 속도 향상, 정확성, 늘어나고 됩니다 더 안정적입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 받아들이는 오버 로드에 문자열 비교 메서드를 변경 합니다 <xref:System.StringComparison?displayProperty=fullName> 열거형을 매개 변수로 지정 **서** 또는 **OrdinalIgnoreCase**합니다. 예를 들어, `String.Compare(str1, str2)`를 `String.Compare(str1, str2, StringComparison.Ordinal)`로 변경합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 라이브러리 또는 응용 프로그램 제한 된 로컬 사용자를 위한 것 때나 현재 문화권의 의미를 사용 해야 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="see-also"></a>참고자료

- [전역화 경고](../code-quality/globalization-warnings.md)
- [CA1307: StringComparison 지정](../code-quality/ca1307-specify-stringcomparison.md)