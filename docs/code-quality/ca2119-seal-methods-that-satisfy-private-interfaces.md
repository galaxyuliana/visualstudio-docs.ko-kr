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
ms.openlocfilehash: 02e69a97468675cd6f7530793581c15717465d6f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921056"
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: private 인터페이스를 만족하는 메서드를 봉인하세요.

|||
|-|-|
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|
|CheckId|CA2119|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
상속 가능한 public 형식은 `internal` (`Friend` Visual Basic) 인터페이스의 재정의 가능한 메서드 구현을 제공 합니다.

## <a name="rule-description"></a>규칙 설명
인터페이스 메서드에는 구현 형식으로 변경할 수 없는 public 액세스 가능성이 있습니다. 내부 인터페이스는 인터페이스를 정의 하는 어셈블리 외부에서 구현 하기에 적합 하지 않은 계약을 만듭니다. `virtual` (`Overridable` Visual Basic) 한정자를 사용 하 여 내부 인터페이스의 메서드를 구현 하는 공용 형식에서 메서드를 어셈블리 외부의 파생 형식으로 재정의할 수 있습니다. 정의 하는 어셈블리의 두 번째 형식에서 메서드를 호출 하 고 내부 전용 계약이 필요한 경우에는 외부 어셈블리의 재정의 된 메서드가 대신 실행 될 때 동작이 손상 될 수 있습니다. 이렇게 하면 보안 취약성이 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 다음 중 하나를 사용 하 여 메서드가 어셈블리 외부에서 재정의 되지 않도록 합니다.

- 선언 형식 `sealed` (`NotInheritable` Visual Basic)을 만듭니다.

- 선언 형식의 액세스 가능성을 ( `internal` `Friend` Visual Basic)로 변경 합니다.

- 선언 형식에서 모든 public 생성자를 제거 합니다.

- 한정자를 `virtual` 사용 하지 않고 메서드를 구현 합니다.

- 메서드를 명시적으로 구현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
신중 하 게 검토 한 후 메서드가 어셈블리 외부에서 재정의 되는 경우 악용 될 수 있는 보안 문제가 없는 경우에는이 규칙에서 경고를 표시 하지 않아도 됩니다.

## <a name="example-1"></a>예제 1
다음 예제에서는이 규칙을 위반 `BaseImplementation`하는 형식을 보여 줍니다.

[!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
[!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
[!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]

## <a name="example-2"></a>예제 2
다음 예제에서는 이전 예제의 가상 메서드 구현을 이용 합니다.

[!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
[!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
[!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]

## <a name="see-also"></a>참고자료

- [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)
- [인터페이스](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)