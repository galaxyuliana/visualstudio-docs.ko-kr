---
title: 'CA1036: 비교 가능한 형식에 메서드를 재정의하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d08644ede6b9b28496cff585624ea37858afd49
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842296"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: 비교 가능한 형식에 메서드를 재정의하세요.

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식이 구현 하는 <xref:System.IComparable?displayProperty=fullName> 인터페이스를 재정의 하지 않습니다 <xref:System.Object.Equals%2A?displayProperty=fullName> 오버 로드 하지 않으므로 같음, 같지 않음에 대 한 언어별 연산자 덜 또는-보다 크거나-보다 합니다. 인터페이스의 구현을 상속 하는 경우 규칙 위반을 보고 하지 않습니다.

기본적으로이 규칙만 살펴봅니다 public 및 protected 형식 이지만 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

사용자 지정 정렬 순서를 정의 하는 형식을 구현 합니다 <xref:System.IComparable> 인터페이스입니다. <xref:System.IComparable.CompareTo%2A> 메서드 형식의 두 인스턴스에 대 한 적절 한 정렬 순서를 나타내는 정수 값을 반환 합니다. 이 규칙에는 정렬 순서를 설정 하는 형식을 식별 합니다. 하다 정렬 순서를 설정 합니다. 같음의 일반 의미, 같지 않음-보다 이상-적용 하지 않습니다. 구현을 제공 하는 경우 <xref:System.IComparable>, 일반적으로 수행 해야 재정의할 수도 <xref:System.Object.Equals%2A> 와 일치 하는 값을 반환할 수 있도록 <xref:System.IComparable.CompareTo%2A>입니다. 재정의 하는 경우 <xref:System.Object.Equals%2A> 코딩 및 연산자 오버 로드를 지 원하는 언어로 일관 된 연산자를 제공 해야 <xref:System.Object.Equals%2A>합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 재정의 <xref:System.Object.Equals%2A>합니다. 프로그래밍 언어가 연산자 오버 로드를 지 원하는 경우에 다음 연산자를 제공 합니다.

- op_Equality
- op_Inequality
- op_LessThan
- op_GreaterThan

C#에서는 이러한 연산자를 나타내는 데 사용 되는 토큰은 다음과 같습니다.

```csharp
==
!=
<
>
```

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

Visual Basic을 사용한 경우 처럼 CA1036 누락 된 연산자와 프로그래밍 언어에서 위반이 발생 하는 경우 연산자 오버 로드를 지원 하지 않습니다 하는 규칙에서 경고를 표시 하지 않으려면 안전 합니다. 연산자를 구현 이해 되지 않는 앱 컨텍스트에서 확인 하는 경우 안전 op_Equality 이외의 같음 연산자에서 발생 하면이 규칙에서 경고를 표시 하 게 이기도 합니다. 그러나 op_Equality 항상 재정의 해야 하며 재정의 하는 경우 연산자 = = <xref:System.Object.Equals%2A?displayProperty=nameWithType>합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1036.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="examples"></a>예제

다음 코드를 올바르게 구현 하는 형식을 포함 <xref:System.IComparable>합니다. 관련 된 다양 한 규칙을 충족 하는 메서드를 식별 하는 코드 주석을 <xref:System.Object.Equals%2A> 하며 <xref:System.IComparable> 인터페이스입니다.

[!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

다음 응용 프로그램 코드의 동작을 테스트 합니다 <xref:System.IComparable> 앞에 나온를 구현 합니다.

[!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)