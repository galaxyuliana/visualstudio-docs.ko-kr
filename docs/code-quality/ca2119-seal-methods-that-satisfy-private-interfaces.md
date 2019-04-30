---
title: 'CA2119: private 인터페이스를 만족하는 메서드를 봉인하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4c019e98e7f1311b6521dff563cb8e7bb0a2356e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62544023"
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: private 인터페이스를 만족하는 메서드를 봉인하세요.

|||
|-|-|
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|
|CheckId|CA2119|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 상속할 수 있는 공용 형식의 재정의 가능한 메서드 구현을 제공 된 `internal` (`Friend` Visual basic에서) 인터페이스입니다.

## <a name="rule-description"></a>규칙 설명
 인터페이스 메서드를 구현 하는 형식으로 변경할 수 없는 public 접근성이 있어야 합니다. 내부 인터페이스에는 인터페이스를 정의 하는 어셈블리 외부에 구현 되도록 디자인 되지 않은 계약을 만듭니다. 사용 하 여 내부 인터페이스 메서드를 구현 하는 공용 형식 합니다 `virtual` (`Overridable` Visual basic에서) 한정자 메서드를 어셈블리 외부에 있는 파생된 된 형식에서 재정의할 수 있습니다. 정의 하는 어셈블리의 두 번째 형식 메서드를 호출 하는 내부 전용 계약 예상 하는 경우에 외부 어셈블리에서 재정의 된 메서드를 실행 하는 대신 하는 경우 동작 손상 될 수 있습니다. 이 보안 취약점을 만듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 다음 중 하나를 사용 하 여 어셈블리 외부에서 재정의 되지 않도록:

- 선언 형식을 `sealed` (`NotInheritable` Visual basic에서).

- 선언 형식의 액세스 가능성을 변경할 `internal` (`Friend` Visual basic에서).

- 선언 형식에서 모든 public 생성자를 제거 합니다.

- 사용 하지 않고 메서드를 구현 합니다 `virtual` 한정자입니다.

- 메서드를 명시적으로 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 경고를 표시 하지 않아도 안전 합니다 신중 하 게 검토 한 후 보안 문제가 있는 경우에 규칙 어셈블리 외부에서 메서드가 재정의 된 경우에 악용 될 수 있습니다.

## <a name="example-1"></a>예제 1
 다음 예제에서는 형식 `BaseImplementation`,이 규칙을 위반 하 합니다.

 [!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
 [!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
 [!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]

## <a name="example-2"></a>예제 2
 다음 예제에서는 이전 예제의 가상 메서드 구현을 이용합니다.

 [!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
 [!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
 [!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]

## <a name="see-also"></a>참고자료

- [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)
- [인터페이스](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)