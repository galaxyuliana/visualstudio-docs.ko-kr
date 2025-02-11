---
title: 'CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2a793f0a359cadc58c262861ee0495f92188d0b7
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547183"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|범주|Microsoft.Naming|
|변경 수준|중단-인터페이스에서 발생 한 경우<br /><br /> 제네릭 형식 매개 변수에 대해 발생 하는 경우를 구분 하지 않습니다.|

## <a name="cause"></a>원인

인터페이스 이름이 대문자 ' I '로 시작 하지 않습니다.

또는

형식 또는 메서드에 대 한 [제네릭 형식 매개 변수의](/dotnet/csharp/programming-guide/generics/generic-type-parameters) 이름이 대문자 ' t '로 시작 하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 인터페이스, 형식 및 메서드만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

규칙에 따라 특정 프로그래밍 요소의 이름이 특정 접두사로 시작 합니다.

인터페이스 이름은 대문자 ' I '로 시작 하 고 또 다른 대문자를 사용 해야 합니다. 이 규칙은 ' MyInterface ' 및 ' IsolatedInterface '과 같은 인터페이스 이름 위반을 보고 합니다.

제네릭 형식 매개 변수 이름은 대문자 ' t '로 시작 해야 하며, 선택적으로 다른 대문자를 사용할 수 있습니다. 이 규칙은 ' V ' 및 ' Type '과 같은 제네릭 형식 매개 변수 이름에 대 한 위반을 보고 합니다.

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요한 학습 곡선이 줄어들고, 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 했을 때 고객의 자신감을 높일 수 있습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우이 규칙을 분석 하는 코드 부분을 구성할 수 있습니다. 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

### <a name="single-character-type-parameters"></a>단일 문자 형식 매개 변수

단일 문자 형식 매개 변수를이 규칙에서 제외할지 여부를 구성할 수 있습니다. 예를 들어이 규칙에서 단일 문자 형식 매개 변수를 분석 *하지* 않도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍 중 하나를 추가 합니다.

```ini
# Package version 2.9.0 and later
dotnet_code_quality.CA1715.exclude_single_letter_type_parameters = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.allow_single_letter_type_parameters = true
```

> [!NOTE]
> 이 규칙은 라는 `T` `Collection<T>`형식 매개 변수에 대해서는 발생 하지 않습니다.

### <a name="api-surface"></a>API 화면

액세스 가능성에 따라이 규칙을 실행할 코드 베이스의 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1715.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명).

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

식별자의 이름을 적절 하 게 접두사로 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="interface-naming-example"></a>인터페이스 명명 예

다음 코드 조각에서는 잘못 명명 된 인터페이스를 보여 줍니다.

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

다음 코드 조각은 인터페이스에 ' I '를 접두사로 사용 하 여 이전 위반을 수정 합니다.

[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="type-parameter-naming-example"></a>형식 매개 변수 명명 예

다음 코드 조각에서는 잘못 명명 된 제네릭 형식 매개 변수를 보여 줍니다.

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

다음 코드 조각에서는 제네릭 형식 매개 변수를 ' t '로 접두사로 사용 하 여 이전 위반을 수정 합니다.

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>관련 규칙

- [CA1722: 식별자에 잘못 된 접두사가 있으면 안 됩니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)