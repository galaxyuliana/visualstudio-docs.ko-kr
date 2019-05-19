---
title: 'CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f666dc71aaf9683d9a7c936cc4985e97146d9454
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842522"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하세요.

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식이 void를 반환 하는 두 매개 변수 (개체가 첫 번째 및 두 번째는 EventArgs에 할당 될 수 있는 형식) 및 포함 된 어셈블리 대상.NET에 포함 된 시그니처 및 대리자를 포함 합니다.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

.NET을 하기 전에 이벤트 처리기에 사용자 지정 정보를 전달 하기 위해 새 대리자를 선언 해야 했습니다에서 파생 된 클래스를 지정 하는 <xref:System.EventArgs?displayProperty=fullName> 클래스입니다. .NET에서 더 이상 마찬가지입니다. 도입 된.NET Framework의 <xref:System.EventHandler%601?displayProperty=fullName> 대리자, 제네릭 대리자에서 파생 되는 모든 클래스를 허용 하는 <xref:System.EventArgs> 이벤트 처리기와 함께 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 대리자를 제거 하 고 사용 하 여 용도 대체 합니다 <xref:System.EventHandler%601?displayProperty=fullName> 위임 합니다.

대리자가 Visual Basic 컴파일러에 의해 자동 생성을 사용 하 여 이벤트 선언의 구문을 변경 된 <xref:System.EventHandler%601?displayProperty=fullName> 위임 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1003.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 대리자를 보여 줍니다. Visual Basic 예제에서는 주석 규칙을 충족 하기 위해 예제를 수정 하는 방법에 설명 합니다. C# 예제에서는 수정 된 코드를 보여 주는 예로가 따릅니다.

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

다음 코드 조각은 규칙을 충족 하는 이전 예제에서 대리자 선언을 제거 합니다. 사용 하는 대체는 `ClassThatRaisesEvent` 하 고 `ClassThatHandlesEvent` 메서드를 사용 하 여는 <xref:System.EventHandler%601?displayProperty=fullName> 위임 합니다.

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1005: 제네릭 형식에 매개 변수를 방지 합니다.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010: 컬렉션에서 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1000: 제네릭 형식에 정적 멤버를 선언 하지 마십시오](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: 제네릭 목록을 노출 하지 마십시오](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: 제네릭 메서드 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1007: 적합 한 제네릭을 사용합니다](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료

- [제네릭](/dotnet/csharp/programming-guide/generics/index)