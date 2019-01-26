---
title: 'CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
helpviewer_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e7059f1babd3ef65c44b3e7192229e3bb56f2c6e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971327"
---
# <a name="ca1712-do-not-prefix-enum-values-with-type-name"></a>CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotPrefixEnumValuesWithTypeName|
|CheckId|CA1712|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 열거형의 형식 이름으로 시작 하는 멤버를 포함 하는 열거형입니다.

## <a name="rule-description"></a>규칙 설명
 열거형 멤버의 이름은 접두사로 사용 하지 않습니다 형식 이름을 있으므로 형식 정보는 개발 도구에서 제공 해야 합니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이 새 소프트웨어 라이브러리에 알아보려면에 필요 하며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 시간을 줄입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 열거형 멤버의 형식 이름 접두사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 수정된 된 버전을 뒤 잘못 명명 된 열거형을 보여 줍니다.

 [!code-csharp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CSharp/ca1712-do-not-prefix-enum-values-with-type-name_1.cs)]
 [!code-cpp[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/CPP/ca1712-do-not-prefix-enum-values-with-type-name_1.cpp)]
 [!code-vb[FxCop.Naming.EnumValues#1](../code-quality/codesnippet/VisualBasic/ca1712-do-not-prefix-enum-values-with-type-name_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1711: 식별자에는 접미사를 사용 해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

 [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.Enum?displayProperty=fullName>