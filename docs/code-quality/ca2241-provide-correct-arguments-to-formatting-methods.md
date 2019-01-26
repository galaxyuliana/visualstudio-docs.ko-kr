---
title: 'CA2241: 서식 지정 메서드에 올바른 인수를 제공하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f723e9c3a6f204b1a19648b121637f42d1fb4017
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920848"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: 서식 지정 메서드에 올바른 인수를 제공하십시오.

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 합니다 `format` 과 같은 메서드에 전달 된 인수를 문자열 <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, 또는 <xref:System.String.Format%2A?displayProperty=fullName> 각 개체 인수 또는 그 반대로 해당 형식 항목이 없습니다.

## <a name="rule-description"></a>규칙 설명
 등의 메서드 인수 <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, 및 <xref:System.String.Format%2A> 형식 문자열 뒤에 여러 개로 <xref:System.Object?displayProperty=fullName> 인스턴스. 형식 문자열을 텍스트 및 포함 된 형식 항목 양식의 이루어져 {인덱스 [, 맞춤] [: formatString]}. 'index'는 형식을 지정할 개체 부분을 나타내는 0부터 시작하는 정수입니다. 개체에 해당 하는 인덱스가 없으면 형식 문자열에서 개체는 무시 됩니다. '인덱스'로 지정 된 개체가 없는 경우는 <xref:System.FormatException?displayProperty=fullName> 런타임에 throw 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 각 개체 인수에 대 한 서식 항목을 제공 하 고 각 서식 항목에 대 한 개체 인수를 제공 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 두 가지 규칙 위반을 보여 줍니다.

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]