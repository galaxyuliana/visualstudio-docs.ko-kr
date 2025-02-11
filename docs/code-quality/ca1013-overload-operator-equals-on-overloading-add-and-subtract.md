---
title: 'CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8c82e7303ea4016974be04c3d8745cb2011017f0
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923168"
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하세요.

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
public 또는 protected 형식이 같음 연산자를 구현하지 않고 더하기 또는 빼기 연산자를 구현합니다.

## <a name="rule-description"></a>규칙 설명
더하기 및 빼기와 같은 작업을 사용 하 여 형식의 인스턴스를 결합할 수 있는 경우에는 거의 항상 같음을 정의 하 여 `true` 동일한 구성 값을 가진 두 인스턴스의 값을 반환 해야 합니다.

같음 연산자의 오버 로드 된 구현에서는 기본 같음 연산자를 사용할 수 없습니다. 이렇게 하면 스택 오버플로가 발생 합니다. 같음 연산자를 구현 하려면 구현에서 개체. Equals 메서드를 사용 합니다. 다음 예제를 참조하세요.

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
이 규칙 위반 문제를 해결 하려면 더하기 및 빼기 연산자와 수학적으로 일치 하도록 같음 연산자를 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
같음 연산자의 기본 구현이 형식에 올바른 동작을 제공 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반`BadAddableType`하는 형식 ()을 정의 합니다. 동일한 필드 값 `true` 이 있는 두 인스턴스가 같은지를 확인 하려면이 형식이 같음 연산자를 구현 해야 합니다. 형식은 `GoodAddableType` 수정 된 구현을 보여 줍니다. 또한이 형식은 같지 않음 연산자 및 재정의 <xref:System.Object.Equals%2A> 를 구현 하 여 다른 규칙을 충족 합니다. 전체 구현에서는도 구현 <xref:System.Object.GetHashCode%2A>합니다.

[!code-csharp[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]

## <a name="example"></a>예제
다음 예제에서는이 항목에서 이전에 정의한 형식의 인스턴스를 사용 하 여 같은지 여부를 테스트 하 여 같음 연산자에 대 한 기본 동작 및 올바른 동작을 보여 줍니다.

[!code-csharp[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Bad type:  {2,2} {2,2} are equal? No
Good type: {3,3} {3,3} are equal? Yes
Good type: {3,3} {3,3} are == ?   Yes
Bad type:  {2,2} {9,9} are equal? No
Good type: {3,3} {9,9} are == ?   No
```

## <a name="see-also"></a>참고자료

- [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)