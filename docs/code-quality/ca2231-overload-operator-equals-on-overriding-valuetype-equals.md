---
title: 'CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fafa4782762e18f1ced8c7f929720e995986ac7a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546873"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

값 형식이를 재정의 <xref:System.Object.Equals%2A?displayProperty=fullName> 하지만 같음 연산자를 구현 하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

대부분의 프로그래밍 언어에는 값 형식에 대 한 같음 연산자 (= =)의 기본 구현이 없습니다. 프로그래밍 언어가 연산자 오버 로드를 지 원하는 경우 같음 연산자를 구현 하는 것을 고려해 야 합니다. 해당 동작은의 <xref:System.Object.Equals%2A>동작과 동일 해야 합니다.

같음 연산자의 오버 로드 된 구현에서는 기본 같음 연산자를 사용할 수 없습니다. 이렇게 하면 스택 오버플로가 발생 합니다. 같음 연산자를 구현 하려면 구현에서 개체. Equals 메서드를 사용 합니다. 예를 들어:

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시 하지 않아도 됩니다. 그러나 가능 하면 같음 연산자를 제공 하는 것이 좋습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca2231.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (사용량). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반 하는 형식을 정의 합니다.

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1046: 참조 형식에 같음 연산자를 오버 로드 하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225: 연산자 오버 로드에는 대체 이름이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: 오버 로드 연산자 equals에 대 한 Override equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Equals를 재정의할 때 GetHashCode 재정의](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>