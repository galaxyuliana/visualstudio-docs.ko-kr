---
title: 'CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10db644fe4cf65a7336ef8bd50dcf62e072e1c46
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922961"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
외부에서 볼 수 있는 unsealed 형식이 public 인터페이스의 명시적 메서드 구현을 제공하면서 외부에서 볼 수 있는 같은 이름의 대체 메서드를 제공하지 않습니다.

## <a name="rule-description"></a>규칙 설명
공용 인터페이스 메서드를 명시적으로 구현 하는 기본 형식을 고려 합니다. 기본 형식에서 파생 되는 형식은 인터페이스로 캐스팅 된 현재 인스턴스 (`this` 의 C#)에 대 한 참조를 통해서만 상속 된 인터페이스 메서드에 액세스할 수 있습니다. 파생 형식이 상속 된 인터페이스 메서드를 다시 구현 하는 경우에는 기본 구현에 더 이상 액세스할 수 없습니다. 현재 인스턴스 참조를 통해 호출 하면 파생 된 구현이 호출 됩니다. 이로 인해 재귀가 발생 하 고 결과적으로 스택 오버플로가 발생 합니다.

이 규칙은 외부에서 볼 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> `Close()` 수 있는 또는 `System.IDisposable.Dispose(Boolean)` 메서드가 제공 될 때의 명시적 구현에 대 한 위반을 보고 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 동일한 기능을 노출 하 고 파생 형식에 표시 되거나 비 명시적 구현으로 변경 되는 새 메서드를 구현 합니다. 주요 변경 사항이 허용 되는 경우에는 형식을 sealed로 설정 하는 것이 좋습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
명시적으로 구현 된 메서드와 동일한 기능을 포함 하지만 이름이 다른 외부적으로 표시 되는 메서드가 제공 되는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하 `ViolatingBase`는 형식 및 위반에 대 한 수정을 보여 `FixedBase`주는 형식을 보여 줍니다.

[!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]

## <a name="see-also"></a>참고자료
[인터페이스](/dotnet/csharp/programming-guide/interfaces/index)