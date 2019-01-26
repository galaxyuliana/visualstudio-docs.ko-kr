---
title: 'CA1023: 다차원 인덱서를 사용하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a9b708b1be65b8aefa34e9f0366a87d6f94b5b5c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55043702"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: 다차원 인덱서를 사용하지 마세요.

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 둘 이상의 인덱스를 사용 하는 public 또는 protected 인덱서를 포함 합니다.

## <a name="rule-description"></a>규칙 설명
 인덱서, 즉 인덱싱된 속성에는 단일 인덱스를 사용 해야 합니다. 다차원 인덱서는 라이브러리의 유용성을 크게 줄일 수 있습니다. 디자인 여러 인덱스에 필요한 경우 형식 논리 데이터 저장소를 나타내는지 여부를 다시 고려해 보아야 합니다. 그러지 않으면 메서드를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 유일한 정수나 문자열 인덱스를 사용 하도록 디자인을 변경 하거나 인덱서 대신 메서드를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에이 규칙에서 경고를 표시 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 `DayOfWeek03`, 규칙을 위반 하는 다차원 인덱서를 사용 하 여 합니다. 인덱스 변환의 형식으로 볼 수 있습니다 및 메서드로 노출 보다 적절 하 게 됩니다. 형식으로 다시 디자인 `RedesignedDayOfWeek03` 규칙을 충족 하도록 합니다.

 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1043: 인덱서에 정수 또는 문자열 인수를 사용 하 여](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024: 적절 한 속성을 사용 합니다.](../code-quality/ca1024-use-properties-where-appropriate.md)