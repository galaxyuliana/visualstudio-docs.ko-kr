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
ms.openlocfilehash: 1c4cf84a292e11b20eb37bee562cd039096e56af
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545308"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하세요.

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

값 형식을 재정의 하지 않는 <xref:System.Object.Equals%2A?displayProperty=fullName> 또는 같음 연산자 (= =) 구현 하지 않습니다. 이 규칙에서 열거형을 확인 하지 않습니다.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

값 형식, 상속 된 구현에 대 한 <xref:System.Object.Equals%2A> 리플렉션 라이브러리를 사용 하 고 모든 필드의 내용을 비교 합니다. Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다. 비교 또는 정렬 인스턴스 수를 예상 하거나 해시 테이블 키로 사용 하는 경우에 값 형식 구현 해야 <xref:System.Object.Equals%2A>합니다. 프로그래밍 언어가 연산자 오버로드를 지원하는 경우 같음 및 같지 않음 연산자의 구현도 제공해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 구현을 제공할 <xref:System.Object.Equals%2A>합니다. 가능한 경우 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

값 형식의 인스턴스를 서로 비교 하지 않을 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1815.api_surface = private, internal
```

이 범주 (성능)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 코드에서는이 규칙을 위반 하는 구조체 (값 형식)를 보여 줍니다.

[!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

다음 코드를 재정의 하 여 위반을 해결 <xref:System.ValueType.Equals%2A?displayProperty=fullName> 및 같음 연산자를 구현 합니다. (= =,! =):

[!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA2224: 같음 연산자를 오버 로드할 때 equals 재정의](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
- [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>