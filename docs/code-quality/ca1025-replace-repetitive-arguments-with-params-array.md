---
title: 'CA1025: 반복 인수를 매개 변수 배열로 바꾸세요.'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5014bfe809cb5d56a22e971833128d1f48d77319
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922975"
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: 반복 인수를 매개 변수 배열로 바꾸세요.

|||
|-|-|
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|
|CheckId|CA1025|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
공용 형식의 public 또는 protected 메서드에는 세 개 이상의 매개 변수가 있으며 마지막 세 매개 변수는 동일한 형식입니다.

## <a name="rule-description"></a>규칙 설명
정확한 인수 수를 알 수 없고 변수 인수가 같은 형식 이거나 동일한 형식으로 전달 될 수 있는 경우 반복 되는 인수 대신 매개 변수 배열을 사용 합니다. 예를 들어 메서드 <xref:System.Console.WriteLine%2A> 는 매개 변수 배열을 사용 하 여 임의 <xref:System.Object> 개수의 인수를 허용 하는 범용 오버 로드를 제공 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 반복 되는 인수를 매개 변수 배열로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시 하지 않는 것이 항상 안전 합니다. 그러나 이러한 디자인으로 인해 유용성 문제가 발생할 수 있습니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]