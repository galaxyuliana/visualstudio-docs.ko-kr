---
title: 'CA1011: 기본 형식을 매개 변수로 전달해 보세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 644c581757a559311b6660a77c4d9190a7361314
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916559"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: 기본 형식을 매개 변수로 전달해 보세요.

|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

메서드 호출 매개 변수의 기본 형식의 멤버만 및 메서드 선언에 파생 형식이 정식 매개 변수가 포함 됩니다.

## <a name="rule-description"></a>규칙 설명

기본 형식이 메서드 선언의 매개 변수로 지정된 경우 기본 형식에서 파생된 모든 형식을 해당 인수로 메서드에 전달할 수 있습니다. 메서드 본문 내에서 인수를 사용 하면 실행 되는 특정 메서드 인수의 형식에 따라 달라 집니다. 파생된 형식에서 제공 하는 추가 기능이 필요 하지 않은, 경우 기본 형식을 사용 하 여를 메서드를 더 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 해당 기본 형식에 매개 변수 형식의 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

- 메서드는 파생된 형식에서 제공 되는 특정 기능이 필요한 경우

     \- 또는 -

- 더 많이 파생 된 형식 또는 파생된 된 유형에 적용 하는 메서드에 전달 됩니다.

이러한 경우 컴파일러 및 런타임에서 제공 하는 강력한 형식 검사로 인해 코드를 보다 강력한 됩니다.

## <a name="example"></a>예제

다음 예제에서는 메서드를 보여 줍니다 `ManipulateFileStream`, 함께만 사용할 수 있는 <xref:System.IO.FileStream> 이 규칙을 위반 하는 개체입니다. 두 번째 메서드를 `ManipulateAnyStream`를 대체 하 여 규칙을 충족 합니다 <xref:System.IO.FileStream> 매개 변수를 사용 하 여를 <xref:System.IO.Stream>입니다.

[!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
[!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
[!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>관련된 규칙

[CA1059: 멤버는 구체적인 특정 형식을 노출 해야](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)