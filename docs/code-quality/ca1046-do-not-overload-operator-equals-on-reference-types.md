---
title: 'CA1046: 참조 형식에 같음 연산자를 오버로드하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d765bfda87fe184256304b86f145f4f02adb7db6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922636"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: 참조 형식에 같음 연산자를 오버로드하지 마세요.

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
공용 또는 중첩 된 공용 참조 형식이 같음 연산자를 오버 로드 합니다.

## <a name="rule-description"></a>규칙 설명
참조 형식의 경우 같음 연산자의 기본 구현은 대부분 항상 올바릅니다. 기본적으로 두 참조는 같은 개체를 가리킬 경우에만 같습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 같음 연산자의 구현을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
참조 형식이 기본 제공 값 형식 처럼 동작 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다. 형식의 인스턴스에서 더하기 또는 빼기를 수행 하는 것이 의미가 있는 경우 같음 연산자를 구현 하 고 위반을 무시 하는 것이 좋습니다.

## <a name="example"></a>예제
다음 예제에서는 두 참조를 비교할 때의 기본 동작을 보여 줍니다.

[!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]

## <a name="example"></a>예제

다음 응용 프로그램은 일부 참조를 비교 합니다.

[!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
a = new (2,2) and b = new (2,2) are equal? No
c and a are equal? Yes
b and a are == ? No
c and a are == ? Yes
```

## <a name="related-rules"></a>관련 규칙

[CA1013: 더하기 및 빼기 오버 로드에 대 한 오버 로드 연산자 equals](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>참고자료

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)