---
title: 'CA1043: 인덱서에 정수 또는 문자열 인수를 사용하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2f140e8678bfb03bc29a21b05f6f3bfada76e9e7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018567"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: 인덱서에 정수 또는 문자열 인수를 사용하세요.

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 아닌 다른 인덱스 형식을 사용 하는 public 또는 protected 인덱서를 포함 <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>하십시오 <xref:System.Object?displayProperty=fullName>, 또는 <xref:System.String?displayProperty=fullName>.

## <a name="rule-description"></a>규칙 설명
 인덱서, 즉 인덱싱된 속성 인덱스에 대 한 정수 또는 문자열 형식을 사용 해야 합니다. 이러한 형식은 일반적으로 사용 데이터 구조를 인덱싱하는 및 라이브러리의 유용성을 증가 시킵니다. 사용 된 <xref:System.Object> 형식 특정 정수 또는 문자열 형식을 디자인 타임에 지정할 수 없는 이러한 경우로만 제한 해야 합니다. 디자인 가지 인덱스에 필요한 경우 형식 논리 데이터 저장소를 나타내는지 여부를 다시 고려해 보아야 합니다. 논리적 데이터 저장소를 나타내지 않는 경우에 메서드를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 정수 또는 문자열 유형으로 인덱스를 변경 하거나 대신 인덱서 메서드를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에이 규칙에서 경고를 표시 합니다.

## <a name="example"></a>예제
 다음 예제에서는 사용 하는 인덱서를 <xref:System.Int32> 인덱스입니다.

 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1023: 다차원 인덱서 설정 되지 않습니다.](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024: 적절 한 속성을 사용 합니다.](../code-quality/ca1024-use-properties-where-appropriate.md)