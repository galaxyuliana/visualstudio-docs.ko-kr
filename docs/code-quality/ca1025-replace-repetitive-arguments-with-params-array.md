---
title: 'CA1025: 반복 인수를 매개 변수 배열로 바꾸세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de109dddf3bc0ddb8cd50df8dc27e81111d4b6df
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54938512"
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: 반복 인수를 매개 변수 배열로 바꾸세요.

|||
|-|-|
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|
|CheckId|CA1025|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 공용 형식에서 public 또는 protected 메서드 세 개 이상의 매개 변수를 있고 마지막 세 매개 변수에 같은 형식입니다.

## <a name="rule-description"></a>규칙 설명
 인수의 정확한 수를 알 수 없는 및 가변 인수가 같은 형식 또는 같은 형식으로 전달할 수 있습니다 하는 경우 매개 변수 배열을 반복 되는 인수 대신 사용 합니다. 예를 들어 합니다 <xref:System.Console.WriteLine%2A> 메서드는 개수에 관계 없이 적용할 매개 변수 배열을 사용 하는 범용 오버 로드를 제공 <xref:System.Object> 인수입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 매개 변수 배열을 사용 하 여 반복 되는 인수를 대체 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙;에서 경고를 표시 하지 않으려면 항상 괜찮습니다. 그러나이 디자인은 사용 편의성 문제를 발생할 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]