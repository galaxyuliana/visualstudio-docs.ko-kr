---
title: 'CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7c1e50c814c22ccddb43e90b41752f3f0bc5797e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986959"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|범주|Microsoft.Naming|
|변경 수준|주요-인터페이스에서 발생 한 경우입니다.<br /><br /> 주요 변경 아님-제네릭 형식 매개 변수에서 발생 한 경우|

## <a name="cause"></a>원인
 외부에 표시 되는 인터페이스의 이름이 대문자 "I'로 시작 하지 않습니다.

 또는

 에 외부적으로 노출 되는 형식 또는 메서드의 제네릭 형식 매개 변수의 이름을 오지 않습니다 대문자를 사용 하 여 ' T '입니다.

## <a name="rule-description"></a>규칙 설명
 규칙에 따라 특정 프로그래밍 요소의 이름을 특정 접두사로 시작합니다.

 인터페이스 이름 'I' 뒤에 다른 문자를 대문자로 시작 해야 합니다. 이 규칙 'MyInterface' 및 'IsolatedInterface'와 같은 인터페이스 이름에 대 한 위반을 보고합니다.

 제네릭 형식 매개 변수 이름을 시작할지 대문자를 사용 하 여 ' T ' 및 필요에 따라 다른 대문자 따라 나올 수 있습니다. 이 규칙에는 'V' 및 'Type'와 같은 제네릭 형식 매개 변수 이름에는 위반 보고합니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 식별자를 이름을 접두사가 올바르게 추가 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 **다음 예제에서는 이름이 잘못 된 인터페이스를 보여 줍니다.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

## <a name="example"></a>예제
 **다음 예제에서는 'I'를 사용 하 여 인터페이스를 접두사로 사용 하 여 위반을 해결 합니다.**

 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="example"></a>예제
 **다음 예제에서는 잘못 명명 된 제네릭 형식 매개 변수를 보여 줍니다.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

## <a name="example"></a>예제
 **' T를 사용 하 여 제네릭 형식 매개 변수를 접두사로 사용 하 여 위반을 해결 하는 다음 예제에서는 '.**

 [!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
 [!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
 [!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1722: 식별자에는 잘못 된 접두사를 사용 해야 합니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)