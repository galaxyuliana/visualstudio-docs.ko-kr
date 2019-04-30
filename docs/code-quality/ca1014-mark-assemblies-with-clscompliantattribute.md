---
title: 'CA1014: CLSCompliantAttribute로 어셈블리를 표시하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0ea7c0d4b9c1d8edea3c2d96f04114db47f3b0d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779510"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: CLSCompliantAttribute로 어셈블리를 표시하세요.

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 어셈블리에 없는 <xref:System.CLSCompliantAttribute?displayProperty=fullName> 특성이 적용 합니다.

## <a name="rule-description"></a>규칙 설명
 CLS(공용 언어 사양)는 어셈블리가 여러 프로그래밍 언어에 사용될 경우 준수해야 하는 명명 제한, 데이터 형식 및 규칙을 정의합니다. 모든 어셈블리와 CLS 규격을 명시적으로 나타내기 위해 것이 좋습니다 <xref:System.CLSCompliantAttribute>합니다. 특성이 어셈블리에 없는 경우에 어셈블리는 규격이 아닙니다.

 CLS 규격 어셈블리의 형식을 포함 하거나 호환 되지 않는 멤버를 입력 하는 것이 가능 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 합니다. 비규격으로 전체 어셈블리를 표시 하는 대신 준수 하지 않는 및 이들이 요소 표시는 형식 또는 형식 멤버를 결정 해야 합니다. 가능한 경우 많은 어셈블리의 모든 기능에 액세스할 수 있도록 비규격 멤버를 CLS 규격 대체 항목을 제공 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 어셈블리를 준수 하지 않으려면 특성을 적용 하 고 해당 값을 설정 `false`합니다.

## <a name="example"></a>예제
 다음 예제에서는 있는 어셈블리는 <xref:System.CLSCompliantAttribute?displayProperty=fullName> CLS 규격 선언 하는 특성이 적용 합니다.

 [!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
 [!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>참고자료

- <xref:System.CLSCompliantAttribute?displayProperty=fullName>
- [언어 독립성 및 언어 독립적 구성 요소](/dotnet/standard/language-independence-and-language-independent-components)