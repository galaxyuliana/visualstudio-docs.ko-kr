---
title: 'CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.'
ms.date: 05/29/2016
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a59346cb70269d4d2b405279fc9ea5573a879b1e
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547011"
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.

|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

봉인 되지 않은 형식의 생성자는 해당 클래스에 정의 된 가상 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명

가상 메서드가 호출 되 면 메서드를 실행 하는 실제 형식이 런타임까지 선택 되지 않습니다. 생성자가 가상 메서드를 호출 하는 경우 메서드를 호출 하는 인스턴스에 대 한 생성자가 실행 되지 않았을 수 있습니다.

> [!NOTE]
> 이 규칙의 레거시 분석 구현에는 클래스에 의해 정의 된 가상**메서드를 호출 하는 호출 체인이 포함 된 "생성자 이름"\[의 진단 메시지가 다릅니다. 의도 하지 않은 결과**를 보려면 다음 호출 스택을 검토 하십시오. " 이 규칙의 [FxCop 분석기](install-fxcop-analyzers.md) 구현에는 "**생성자에서 재정의할 수 있는 메서드를 호출 하지**않습니다." 라는 진단 메시지가 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 형식의 생성자 내에서 형식의 가상 메서드를 호출 하지 마십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 가상 메서드에 대 한 호출을 제거 하려면 생성자를 다시 디자인 해야 합니다.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반 하는 경우의 영향을 보여 줍니다. 테스트 응용 프로그램은 기본 클래스 ( `DerivedType``BadlyConstructedType`) 생성자를 실행 하는 인스턴스를 만듭니다. `BadlyConstructedType`의 생성자가 가상 메서드 `DoSomething`를 잘못 호출 합니다. 출력에 표시 된 것 `DerivedType.DoSomething()` 처럼는 `DerivedType`생성자가 실행 되기 전에 실행 됩니다.

[!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
[!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Calling base ctor.
Derived DoSomething is called - initialized ? No
Calling derived ctor.
```