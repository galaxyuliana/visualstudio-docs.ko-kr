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
ms.openlocfilehash: 2a4e04e1afdbecdc9c333ea43a52bff3123d448a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547626"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: 비교 가능한 형식에 메서드를 재정의하세요.

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

형식은 인터페이스를 <xref:System.IComparable?displayProperty=fullName> 구현 하며, 같음, 같지 <xref:System.Object.Equals%2A?displayProperty=fullName> 않음, 보다 작음 또는 보다 큼을 위해 언어별 연산자를 재정의 하거나 오버 로드 하지 않습니다. 형식이 인터페이스의 구현만 상속 하는 경우 규칙에서 위반을 보고 하지 않습니다.

기본적으로이 규칙은 공용 및 보호 된 형식만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

사용자 지정 정렬 순서를 정의 하는 형식은 <xref:System.IComparable> 인터페이스를 구현 합니다. 메서드 <xref:System.IComparable.CompareTo%2A> 는 형식의 두 인스턴스에 대 한 올바른 정렬 순서를 나타내는 정수 값을 반환 합니다. 이 규칙은 정렬 순서를 설정 하는 형식을 식별 합니다. 정렬 순서를 설정 하는 것은 같음, 같지 않음, 보다 작음 및 보다 큼의 일반적인 의미가 적용 되지 않는다는 것을 의미 합니다. 의 <xref:System.IComparable>구현을 제공 하는 경우 일반적으로와 <xref:System.IComparable.CompareTo%2A>일치 하는 <xref:System.Object.Equals%2A> 값을 반환 하도록를 재정의 해야 합니다. 연산자 오버 로드 <xref:System.Object.Equals%2A> 를 지 원하는 언어에서를 재정의 하 고 코딩 하는 경우와 <xref:System.Object.Equals%2A>일치 하는 연산자도 제공 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면를 재정의 <xref:System.Object.Equals%2A>합니다. 프로그래밍 언어가 연산자 오버 로드를 지 원하는 경우 다음 연산자를 제공 합니다.

- op_Equality
- op_Inequality
- op_LessThan
- op_GreaterThan

에서 C#이러한 연산자를 나타내는 데 사용 되는 토큰은 다음과 같습니다.

```csharp
==
!=
<
>
```

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

Visual Basic의 경우와 마찬가지로 위반으로 인해 위반이 발생 하 고 프로그래밍 언어가 연산자 오버 로드를 지원 하지 않는 경우에는 rule CA1036에서 경고를 무시 해도 안전 합니다. 응용 프로그램 컨텍스트에서 연산자를 구현 하는 것이 적합 하지 않은 것으로 확인 되 면 op_Equality가 아닌 같음 연산자에서 발생 하는 경우이 규칙에서 경고를 표시 하지 않아도 됩니다. 그러나를 재정의 <xref:System.Object.Equals%2A?displayProperty=nameWithType>하는 경우 항상 op_Equality 및 = = 연산자를 재정의 해야 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1036.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="examples"></a>예

다음 코드에는를 올바르게 구현 <xref:System.IComparable>하는 형식이 포함 되어 있습니다. 코드 주석은 <xref:System.Object.Equals%2A> <xref:System.IComparable> 및 인터페이스와 관련 된 다양 한 규칙을 충족 하는 메서드를 식별 합니다.

[!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

다음 응용 프로그램 코드는 앞에서 설명한 <xref:System.IComparable> 구현의 동작을 테스트 합니다.

[!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)