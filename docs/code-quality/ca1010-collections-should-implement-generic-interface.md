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
ms.openlocfilehash: 70a418b211cd4340dba9c15f0bf52e3cdfdf8e8f
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547906"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

형식은 <xref:System.Collections.IEnumerable?displayProperty=fullName> 인터페이스를 구현 하지만 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 구현 하지 않으며 포함 하는 어셈블리가 .net을 대상으로 합니다. 이 규칙은를 구현 <xref:System.Collections.IDictionary?displayProperty=fullName>하는 형식을 무시 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

컬렉션의 유용성을 높이려면 제네릭 컬렉션 인터페이스 중 하나를 구현합니다. 그런 다음 컬렉션을 사용 하 여 다음과 같은 제네릭 컬렉션 형식을 채울 수 있습니다.

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 다음 제네릭 컬렉션 인터페이스 중 하나를 구현 합니다.

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시 하지 않아도 됩니다. 그러나 컬렉션을 사용 하는 것이 더 제한적입니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1010.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example-violation"></a>위반 예

다음 예제에서는이 규칙을 위반 하는 제네릭이 `CollectionBase` 아닌 클래스에서 파생 되는 클래스 (참조 형식)를 보여 줍니다.

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

이 규칙 위반 문제를 해결 하려면 다음 중 하나를 수행 합니다.

- 제네릭 인터페이스를 구현 합니다.
- 기본 클래스를 `Collection<T>` 클래스와 같은 제네릭 및 비 제네릭 인터페이스를 이미 구현 하는 형식으로 변경 합니다.

## <a name="fix-by-base-class-change"></a>기본 클래스 변경에의 한 수정

다음 예제에서는 컬렉션의 기본 클래스를 제네릭이 `CollectionBase` 아닌 클래스에서 제네릭 `Collection<T>` (`Collection(Of T)` Visual Basic) 클래스로 변경 하 여 위반을 수정 합니다.

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

이미 릴리스된 클래스의 기본 클래스를 변경 하는 것은 기존 소비자의 주요 변경 내용으로 간주 됩니다.

## <a name="fix-by-interface-implementation"></a>인터페이스 구현에 의해 수정

다음 `IEnumerable<T>`예제에서는,, `ICollection<T>` `IList<T>` `IEnumerable(Of T)` 및(`ICollection(Of T)`Visual Basic) 의제네릭인터페이스를구현하여위반을수정합니다.`IList(Of T)`

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1005: 제네릭 형식에 대 한 과도 한 매개 변수 방지](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000: 정적 멤버를 제네릭 형식으로 선언 하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: 제네릭 목록을 노출 하지 않습니다.](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: 제네릭 메서드는 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003: 제네릭 이벤트 처리기 인스턴스 사용](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007: 적절 한 경우 제네릭을 사용 합니다.](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료

- [제네릭](/dotnet/csharp/programming-guide/generics/index)