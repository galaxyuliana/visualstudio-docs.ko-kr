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
ms.openlocfilehash: a1ef4258d1b095395be34c7004e3f783b973897d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547884"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하세요.

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식에는 void를 반환 하는 대리자가 포함 되 고 해당 시그니처에는 두 개의 매개 변수 (첫 번째 개체와 EventArgs에 할당할 수 있는 두 번째 형식)가 포함 되며 포함 하는 어셈블리가 .NET을 대상으로 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

.Net 이전에는 사용자 지정 정보를 이벤트 처리기에 전달 하기 위해 <xref:System.EventArgs?displayProperty=fullName> 클래스에서 파생 된 클래스를 지정 하는 새 대리자를 선언 해야 했습니다. .Net에서는 제네릭 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하 여에서 <xref:System.EventArgs> 파생 된 모든 클래스를 이벤트 처리기와 함께 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 대리자를 제거 하 고 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하 여 사용을 바꿉니다.

대리자가 Visual Basic 컴파일러에 의해 자동으로 생성 되는 경우 <xref:System.EventHandler%601?displayProperty=fullName> 대리자를 사용 하도록 이벤트 선언 구문을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1003.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 대리자를 보여 줍니다. Visual Basic 예제에서 주석은 규칙을 충족 하도록 예제를 수정 하는 방법을 설명 합니다. C# 예제에서 수정 된 코드를 보여 주는 예제는 다음과 같습니다.

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

다음 코드 조각에서는 규칙을 충족 하는 이전 예제에서 대리자 선언을 제거 합니다. 대리자를 `ClassThatRaisesEvent` `ClassThatHandlesEvent` 사용하여및메서드에서사용되는<xref:System.EventHandler%601?displayProperty=fullName> 를 대체 합니다.

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1005: 제네릭 형식에 대 한 과도 한 매개 변수 방지](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010: 컬렉션은 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1000: 정적 멤버를 제네릭 형식으로 선언 하지 마십시오.](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: 제네릭 목록을 노출 하지 않습니다.](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: 제네릭 메서드는 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1007: 적절 한 경우 제네릭을 사용 합니다.](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>참고자료

- [제네릭](/dotnet/csharp/programming-guide/generics/index)