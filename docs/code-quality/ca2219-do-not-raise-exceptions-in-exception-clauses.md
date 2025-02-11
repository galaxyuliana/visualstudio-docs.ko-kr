---
title: 'CA2219: exception 절에서 예외를 발생시키지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f8e949e21530654882cba99a7d9fedad8b5b59b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920265"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: exception 절에서 예외를 발생시키지 마세요.

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|범주|Microsoft.Usage|
|변경 수준|분리 안, 중단|

## <a name="cause"></a>원인
`finally`, 필터 또는 fault 절에서 예외가 throw 됩니다.

## <a name="rule-description"></a>규칙 설명
예외 절에서 예외가 발생 하면 디버깅의 어려움이 크게 향상 됩니다.

`finally` 또는 fault 절에서 예외가 발생 하면 새 예외가 활성 예외 (있는 경우)를 숨깁니다. 이렇게 하면 원래 오류를 검색 하 고 디버그 하기가 어렵습니다.

필터 절에서 예외가 발생 하면 런타임은 예외를 자동으로 catch 하 고 필터를 false로 평가 합니다. False로 평가 되는 필터와 필터에서 throw 되는 예외 간의 차이를 알 수 있는 방법은 없습니다. 이렇게 하면 필터 논리에서 오류를 검색 하 고 디버그 하기가 어렵습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 `finally`, 필터 또는 fault 절에서 명시적으로 예외를 발생 시 키 지 마십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에 대 한 경고를 표시 하지 않습니다. 예외 절에서 발생 하는 예외가 실행 코드에 대 한 이점을 제공 하는 시나리오는 없습니다.

## <a name="related-rules"></a>관련 규칙
[CA1065: 예기치 않은 위치에서 예외를 발생 시 키 지 마십시오.](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>참고자료
[디자인 경고](../code-quality/design-warnings.md)