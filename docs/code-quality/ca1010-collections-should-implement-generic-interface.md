---
title: 'CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c71912fdd70226e1b4be3c14be7c4e0bac26259d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779848"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식이 구현 하는 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현 하지 않습니다 하지만 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 포함 하는 어셈블리 대상.NET. 이 규칙을 구현 하는 형식을 무시 <xref:System.Collections.IDictionary?displayProperty=fullName>합니다.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

컬렉션의 유용성을 높이려면 제네릭 컬렉션 인터페이스 중 하나를 구현합니다. 그런 다음 다음과 같은 제네릭 컬렉션 형식을 채울 컬렉션을 사용할 수 있습니다.

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 다음과 같은 제네릭 컬렉션 인터페이스 중 하나를 구현 합니다.

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙;에서 경고를 표시 하지 않아도 안전 합니다. 그러나 컬렉션의 사용 보다 제한 됩니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1010.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example-violation"></a>예제 위반

다음 예제에서는 비 제네릭에서 파생 된 클래스 (참조 형식)를 보여 줍니다. `CollectionBase` 이 규칙을 위반 하는 클래스입니다.

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

이 규칙 위반 문제를 해결 하려면 다음 중 하나를 수행 합니다.

- 제네릭 인터페이스를 구현 합니다.
- 이미 등 모두를 제네릭 및 제네릭이 아닌 인터페이스를 구현 하는 형식으로 기본 클래스를 변경 합니다 `Collection<T>` 클래스입니다.

## <a name="fix-by-base-class-change"></a>기본 클래스를 변경 하 여 해결

다음 예제에서 제네릭이 아닌 컬렉션의 기본 클래스를 변경 하 여 위반을 수정 `CollectionBase` 제네릭 클래스 `Collection<T>` (`Collection(Of T)` Visual Basic에서) 클래스입니다.

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

이미 발표 된 클래스의 기본 클래스를 변경 하면 기존 소비자에 게 주요 변경 내용으로 간주 됩니다.

## <a name="fix-by-interface-implementation"></a>인터페이스 구현에 의해 수정

다음 예제에서는 이러한 제네릭 인터페이스를 구현 하 여 위반을 수정: `IEnumerable<T>`, `ICollection<T>`, 및 `IList<T>` (`IEnumerable(Of T)`를 `ICollection(Of T)`, 및 `IList(Of T)` Visual basic에서).

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1005: 제네릭 형식에 매개 변수를 방지 합니다.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000: 제네릭 형식에 정적 멤버를 선언 하지 마십시오](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: 제네릭 목록을 노출 하지 마십시오](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: 제네릭 메서드 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용 합니다.](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007: 적합 한 제네릭을 사용합니다](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료

- [제네릭](/dotnet/csharp/programming-guide/generics/index)