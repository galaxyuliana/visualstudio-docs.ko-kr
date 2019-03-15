---
title: 'CA1052: 정적 소유자 형식은 sealed여야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 46a8c9a4e22c7a54a4b2b68f95bb2b81f3a0888e
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57870388"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: 정적 소유자 형식은 sealed여야 합니다.

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

추상이 아닌 정적 멤버만 포함 형식과로 선언 되지 않습니다 합니다 [봉인](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) 한정자.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

규칙 CA1052 형식에서 파생된 된 형식에서 재정의할 수 있는 모든 기능을 제공 하지 않으므로 정적 멤버만 포함 하는 형식에서 상속 하도록 설계 되지 않았습니다 하는 것으로 가정 합니다. 상속 고려 하지 않은 형식을 사용 하 여 표시 됨을 `sealed` 또는 `NotInheritable` 한정자 기본 형식으로 사용 되지 않도록 합니다. 이 규칙은 추상 클래스에 대 한 발생 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 형식 표시 `sealed` 또는 `NotInheritable`합니다. .NET Framework 2.0을 대상으로 하는 경우 더 나은 방법으로 형식을 표시 하는 것 이상을 `static` 또는 `Shared`합니다. 이런 방식으로 만들어지는 클래스를 방지 하기 위해 개인 생성자를 선언할 필요가 없습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

형식 상속 하도록 하는 경우에이 규칙에서 경고를 표시 합니다. 없는 경우는 `sealed` 또는 `NotInheritable` 한정자 제안 형식이 기본 형식으로 유용 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1052.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example-of-a-violation"></a>위반의 예

다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Static 한정자를 사용 하 여 해결

다음 예제에서는 사용 하 여 형식을 표시 하 여이 규칙 위반 문제를 해결 하는 방법을 보여 줍니다 합니다 `static` 한정자 C#:

[!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1053: 정적 소유자 형식에는 생성자를 사용 해야 합니다.](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)