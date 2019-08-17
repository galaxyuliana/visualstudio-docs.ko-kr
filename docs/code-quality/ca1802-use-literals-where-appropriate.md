---
title: 'CA1802: 가능하면 리터럴을 사용하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c6512f02d13c2eeb441f5b374c4785deffe22a22
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547058"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: 가능하면 리터럴을 사용하세요.

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|범주|Microsoft.Performance|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

필드는 및 `readonly` ( `static` `Shared` Visual Basic )로선언되고컴파일타임에계산할수값으로초기화됩니다.`ReadOnly`

기본적으로이 규칙은 외부에서 볼 수 있는 필드만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

선언 형식에 대 `static readonly` 한 정적 생성자가 호출 될 때 필드의 값은 런타임에 계산 됩니다. `static readonly` 필드가 선언 될 때 초기화 되 고 정적 생성자가 명시적으로 선언 되지 않은 경우 컴파일러는 정적 생성자를 내보내 필드를 초기화 합니다.

`const` 필드의 값은 컴파일 시간에 계산 되 고 메타 데이터에 저장 되므로 `static readonly` 필드와 비교할 때 런타임 성능이 향상 됩니다.

대상 필드에 할당 된 값은 컴파일 시간에 계산할 수 때문에 런타임이 아닌 컴파일 시간에 값 `const` 이 계산 되도록 선언을 필드로 변경 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 `static` 및 `readonly` 한정자를 `const` 한정자로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

성능이 중요 하지 않은 경우이 규칙에서 경고를 표시 하지 않거나 규칙을 사용 하지 않도록 설정 하는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1802.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나 모든 규칙에 대해이 옵션을 구성 하거나이 범주 (성능)의 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하 `UseReadOnly`는, 및 규칙을 충족 하는 `UseConstant`형식을 보여 줍니다.

[!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
[!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]