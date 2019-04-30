---
title: 'CA2218: Equals를 재정할 때 GetHashCode를 재정의하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 155d983a68734038220ffb53aa7a5e9504abdb40
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541886"
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218: Equals를 재정할 때 GetHashCode를 재정의하세요.

|||
|-|-|
|TypeName|OverrideGetHashCodeOnOverridingEquals|
|CheckId|CA2218|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 형식이 재정의 <xref:System.Object.Equals%2A?displayProperty=fullName> 를 재정의 하지 않습니다 하지만 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>합니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.Object.GetHashCode%2A> 해시 알고리즘 및 해시 테이블과 같은 데이터 구조에 적합 하는 현재 인스턴스를 기반으로 값을 반환 합니다. 두 개체가 동일한 형식이 고 같은지 여부를 지정 하는 다음 형식의 인스턴스가 올바르게 작동 하도록 동일한 해시 코드를 반환 해야 합니다.

- <xref:System.Collections.Hashtable?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>

- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>

- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>

- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>

- <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>

- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>

- 구현 하는 형식 <xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 구현을 제공할 <xref:System.Object.GetHashCode%2A>합니다. 같은 형식의 개체 쌍을 확인 해야 합니다는 구현 하는 경우 같은 값을 반환 하는 구현의 <xref:System.Object.Equals%2A> 반환 `true` 쌍을 찾습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="class-example"></a>클래스 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 클래스 (참조 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]

### <a name="comments"></a>설명
 다음 예제에서는 재정의 하 여 위반 수정 <xref:System.Object.GetHashCode>합니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]

## <a name="structure-example"></a>구조 예제

### <a name="description"></a>설명
 다음 예제에서는이 규칙을 위반 하는 구조체 (값 형식)를 보여 줍니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]

### <a name="comments"></a>설명
 다음 예제에서는 재정의 하 여 위반 수정 <xref:System.Object.GetHashCode>합니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA1046: 참조 형식에 같음 연산자 오버 로드 하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: 연산자 오버 로드는 명명 된 대체](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: 같음 연산자를 오버 로드할 때 equals 재정의](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- <xref:System.Object.GetHashCode%2A?displayProperty=fullName>
- <xref:System.Collections.Hashtable?displayProperty=fullName>
- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)