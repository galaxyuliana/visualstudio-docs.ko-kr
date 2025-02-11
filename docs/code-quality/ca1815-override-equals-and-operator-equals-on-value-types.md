---
title: 'CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97f56e406d00de1891647c4211d21336f9d1a266
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547053"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하세요.

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|범주|Microsoft.Performance|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

값 형식이 연산자를 재정의 <xref:System.Object.Equals%2A?displayProperty=fullName> 하지 않거나 (= =) 연산자를 구현 하지 않습니다. 이 규칙은 열거형을 확인 하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

값 형식의 경우의 <xref:System.Object.Equals%2A> 상속 된 구현에서는 리플렉션 라이브러리를 사용 하 고 모든 필드의 내용을 비교 합니다. Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다. 사용자가 인스턴스를 비교 또는 정렬 하거나 해시 테이블 키로 사용할 것으로 간주 되는 경우 값 형식은를 구현 <xref:System.Object.Equals%2A>해야 합니다. 프로그래밍 언어가 연산자 오버로드를 지원하는 경우 같음 및 같지 않음 연산자의 구현도 제공해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면의 <xref:System.Object.Equals%2A>구현을 제공 합니다. 가능 하면 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

값 형식의 인스턴스를 서로 비교 하지 않을 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1815.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나 모든 규칙에 대해이 옵션을 구성 하거나이 범주 (성능)의 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 코드에서는이 규칙을 위반 하는 구조체 (값 형식)를 보여 줍니다.

[!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

다음 코드에서는 같음 연산자 (= =, <xref:System.ValueType.Equals%2A?displayProperty=fullName> ! =)를 재정의 하 고 구현 하 여 이전 위반을 수정 합니다.

[!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA2224: 오버 로드 연산자 equals에 대 한 Override equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
- [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>