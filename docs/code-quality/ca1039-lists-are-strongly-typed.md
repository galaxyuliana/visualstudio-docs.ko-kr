---
title: 'CA1039: 목록은 강력한 형식이어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94b1e8134eb89e4ae78ec0ad6f07fd7406215185
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922834"
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039: 목록은 강력한 형식이어야 합니다.

|||
|-|-|
|TypeName|ListsAreStronglyTyped|
|CheckId|CA1039|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

Public 또는 protected 형식은를 구현 <xref:System.Collections.IList?displayProperty=fullName> 하지만 다음 중 하나 이상의 강력한 형식의 메서드를 제공 하지 않습니다.

- IList.Item

- IList.Add

- IList.Contains

- IList.IndexOf

- IList.Insert

- IList.Remove

## <a name="rule-description"></a>규칙 설명

사용자가 인터페이스 <xref:System.Collections.IList> 에서 제공 하는 기능을 사용할 때 <xref:System.Object?displayProperty=fullName> 형식으로 인수를 캐스팅할 필요가 없도록이 규칙에서는 구현이 강력한 형식의 멤버를 제공 해야 합니다. 인터페이스 <xref:System.Collections.IList> 는 인덱스에서 액세스할 수 있는 개체의 컬렉션에 의해 구현 됩니다. 이 규칙에서는을 구현 <xref:System.Collections.IList> 하는 형식이 보다 <xref:System.Object>강력한 형식의 인스턴스 컬렉션을 관리 한다고 가정 합니다.

<xref:System.Collections.IList><xref:System.Collections.ICollection?displayProperty=fullName> 및<xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현 합니다. 을 구현 <xref:System.Collections.IList>하는 경우에 <xref:System.Collections.ICollection>필요한 강력한 형식의 멤버를 제공 해야 합니다. 컬렉션의 개체가 확장 <xref:System.ValueType?displayProperty=fullName>되는 경우 boxing으로 인해 발생 하는 성능 저하를 방지 하기 위해에 대 한 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 강력한 형식의 멤버를 제공 해야 합니다 .이는 컬렉션의 개체가 참조 형식이 면 필요 하지 않습니다.

이 규칙을 준수 하려면 InterfaceName. InterfaceMemberName 형식의 이름을 사용 하 여 명시적으로 인터페이스 멤버를 구현 <xref:System.Collections.IList.Add%2A>합니다 (예:). 명시적 인터페이스 멤버는 인터페이스에서 선언 된 데이터 형식을 사용 합니다. 인터페이스 멤버 이름 (예: `Add`)을 사용 하 여 강력한 형식의 멤버를 구현 합니다. 강력한 형식의 멤버를 public으로 선언 하 고, 매개 변수 및 반환 값을 컬렉션에서 관리 되는 강력한 형식으로 선언 합니다. 강력한 형식은 인터페이스에 의해 선언 된 및 <xref:System.Object> <xref:System.Array> 와 같은 약한 형식을 대체 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 명시적으로 멤버 <xref:System.Collections.IList> 를 구현 하 고 이전에 언급 된 멤버에 대해 강력한 형식의 대안을 제공 합니다. 인터페이스를 <xref:System.Collections.IList> 올바르게 구현 하 고 필요한 강력한 형식의 멤버를 제공 하는 코드의 경우 다음 예제를 참조 하세요.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
새 컬렉션을 확장 하는 형식에서 강력한 형식을 결정 하는 연결 된 목록과 같은 새 개체 기반 컬렉션을 구현 하는 경우에는이 규칙의 경고를 표시 하지 않습니다. 이러한 형식은이 규칙을 준수 하 고 강력한 형식의 멤버를 노출 해야 합니다.

## <a name="example"></a>예제
다음 예제에서 형식은 `YourType` 강력한 형식의 모든 컬렉션에 대해를 확장 <xref:System.Collections.CollectionBase?displayProperty=fullName>합니다. <xref:System.Collections.CollectionBase><xref:System.Collections.IList> 인터페이스의 명시적 구현을 제공 합니다. 따라서 및 <xref:System.Collections.IList> <xref:System.Collections.ICollection>에 대해 강력한 형식의 멤버를 제공 해야 합니다.

[!code-csharp[FxCop.Design.IListStrongTypes#1](../code-quality/codesnippet/CSharp/ca1039-lists-are-strongly-typed_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

[CA1038: 열거자는 강력한 형식 이어야 합니다.](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

## <a name="see-also"></a>참고자료

- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.ICollection?displayProperty=fullName>
- <xref:System.Collections.IEnumerable?displayProperty=fullName>
- <xref:System.Collections.IList?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>