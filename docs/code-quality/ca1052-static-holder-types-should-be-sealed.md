---
title: 'CA1052: 정적 소유자 형식은 정적 또는 NotInheritable 이어야 합니다.'
ms.date: 07/25/2019
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
ms.openlocfilehash: ba54b9f87fe8c8cd8bfdc86f39e3121135241e92
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547524"
---
# <a name="ca1052-static-holder-types-should-be-static-or-notinheritable"></a>CA1052: 정적 소유자 형식은 정적 또는 NotInheritable 이어야 합니다.

|||
|-|-|
|TypeName|StaticHolderTypesAnalyzer|
|CheckId|CA1052|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

비추상 형식에는 정적 멤버 (가능한 기본 생성자 제외)만 포함 되며 [static](/dotnet/csharp/language-reference/keywords/static) 또는 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared) 한정자로 선언 되지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

규칙 CA1052는 파생 형식에서 재정의할 수 있는 기능을 제공 하지 않으므로 정적 멤버만 포함 하는 형식이 상속 되지 않는다고 가정 합니다. 상속 되지 않는 형식은 기본 형식으로 사용할 수 없도록의 `static` C# 한정자로 표시 되어야 합니다. 또한 해당 기본 생성자를 제거 해야 합니다. Visual Basic에서 클래스가 [모듈로](/dotnet/visual-basic/language-reference/statements/module-statement)변환 되어야 합니다.

이 규칙은 기본 클래스가 있는 추상 클래스 또는 클래스에 대해 발생 하지 않습니다. 그러나이 규칙은 빈 인터페이스를 지 원하는 클래스에 대해 발생 합니다.

> [!NOTE]
> 이 규칙의 FxCop 분석기 구현에서는 [RULE CA1053](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)의 기능도 포함 되어 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 형식을로 `static` 표시 하 고 기본 생성자 (C#)를 제거 하거나 모듈 (Visual Basic)으로 변환 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

형식을 상속 하도록 디자인 된 경우에만이 규칙에서 경고를 표시 하지 않습니다. `static` 한정자가 없으면 형식이 기본 형식으로 유용한 것으로 제안 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 EditorConfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1052.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example-of-a-violation"></a>위반 예

다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Static 한정자를 사용 하 여 수정

다음 예제에서는에서 `static` C#형식을 한정자로 표시 하 여이 규칙 위반 문제를 해결 하는 방법을 보여 줍니다.

```csharp
public static class StaticMembers
{
    public static int SomeProperty { get; set; }
    public static void SomeMethod() { }
}
```