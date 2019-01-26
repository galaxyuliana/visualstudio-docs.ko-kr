---
title: 'CA1800: 불필요하게 캐스트하지 마세요.'
ms.date: 10/26/2017
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 19ea831e1cec04d6ccce7e35137b6f02bac4b08c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971678"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: 불필요하게 캐스트하지 마세요.

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
메서드 인수 또는 지역 변수 중 하나에서 중복 캐스팅을 수행합니다.

이 규칙에 의해 완벽 하 게 분석에 대 한 디버깅 정보를 사용 하 여 테스트 어셈블리를 작성 해야 하 고 연결된 프로그램 데이터베이스 (.pdb) 파일을 사용할 수 있어야 합니다.

## <a name="rule-description"></a>규칙 설명
중복 캐스팅을 수행하면 성능이 저하됩니다. 특히 간단한 반복 문에서 캐스팅이 수행될 때 더욱 그러합니다. 중복 된 명시적 캐스트 작업을 지역 변수에 캐스팅의 결과 저장 하 고 중복 캐스팅 작업 대신 지역 변수를 사용 합니다.

하는 경우 C# `is` 연산자 실제 캐스팅을 수행 하려면 먼저 캐스트의 성공 여부를 테스트 하는 결과 테스트 하는 것이 좋습니다는 `as` 연산자 대신 합니다. 수행 되는 암시적 캐스트 작업 하지 않고 동일한 기능을 제공 합니다 `is` 연산자입니다. 또는 사용 하 여 C# 7.0 이상 버전에서는 합니다 `is` 연산자 [패턴 일치](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) 형식 변환 확인을 한 번에 해당 형식의 변수로 식을 캐스팅 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 캐스트 연산 수를 최소화 하는 메서드 구현을 수정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 성능이 중요 하지 않은 경우이 규칙에서 경고를 표시 하거나 규칙을 완전히 무시 해도 안전 합니다.

## <a name="examples"></a>예제
 다음 예제에서는 C#을 사용 하 여 규칙을 위반 하는 메서드를 보여 줍니다. `is` 연산자입니다. 대체 하 여 규칙을 충족 하는 두 번째 메서드는 `is` 연산자의 결과 대 한 테스트를 사용 하 여는 `as` 두 반복 당 캐스트 작업 수가 감소 하는 연산자가 있습니다. 또한 세 번째 메서드를 사용 하 여 규칙을 충족 `is` 사용 하 여 [패턴 일치](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) 유형 변환에 성공 하는 경우 원하는 형식의 변수를 만들려고 합니다.

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]

 다음 예제에서는 메서드를 보여 줍니다 `start_Click`, 여러 중복 된 명시적 캐스팅을 설정 하는, 규칙을 위반 하는 메서드는이 있는 `reset_Click`, 캐스팅을 지역 변수에 저장 하 여 규칙을 충족 하는 합니다.

 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]

## <a name="see-also"></a>참고자료

- [as (C# 참조)](/dotnet/csharp/language-reference/keywords/as)
- [is (C# 참조)](/dotnet/csharp/language-reference/keywords/is)