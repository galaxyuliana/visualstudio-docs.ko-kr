---
title: 'CA2134: 메서드는 기본 메서드를 재정의할 때 일관된 투명도를 유지해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ca28f364307d4a2b73235bc6541cb8aa01abd56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920653"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: 메서드는 기본 메서드를 재정의할 때 일관된 투명도를 유지해야 합니다.

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
이 규칙은 <xref:System.Security.SecurityCriticalAttribute> 로 표시 된 메서드가 투명 하거나 <xref:System.Security.SecuritySafeCriticalAttribute>로 표시 된 메서드를 재정의 하는 경우에 발생 합니다. 규칙은 투명 하거나로 <xref:System.Security.SecuritySafeCriticalAttribute> 표시 된 메서드가로 표시 <xref:System.Security.SecurityCriticalAttribute>된 메서드를 재정의 하는 경우에도 발생 합니다.

이 규칙은 가상 메서드를 재정의하거나 인터페이스를 구현할 때 적용됩니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 상속 체인이 추가 된 메서드의 보안 액세스 가능성을 변경 하려고 할 때 발생 합니다. 예를 들어 기본 클래스의 가상 메서드가 투명 하거나 안전에 중요 한 경우 파생 클래스는 투명 하거나 안전에 중요 한 메서드를 사용 하 여 재정의 해야 합니다. 반대로, 가상이 보안에 중요 한 경우 파생 클래스는 보안에 중요 한 메서드를 사용 하 여 재정의 해야 합니다. 인터페이스 메서드를 구현 하는 경우에도 동일한 규칙이 적용 됩니다.

투명도 규칙은 코드가 런타임에 JIT로 컴파일될 때 적용 되므로 투명도 계산에 동적 형식 정보가 포함 되지 않습니다. 따라서 투명도 계산 결과는 동적 형식에 관계 없이 JIT 컴파일되는 정적 형식 에서만 확인할 수 있어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 가상 메서드를 재정의 하거나 인터페이스를 구현 하는 메서드의 투명도를 가상 또는 인터페이스 메서드의 투명도와 일치 하도록 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서 경고를 표시 하지 않습니다. 이 규칙을 위반 하면 수준 2 투명도를 <xref:System.TypeLoadException> 사용 하는 어셈블리에 대 한 런타임이 생성 됩니다.

## <a name="examples"></a>예

### <a name="code"></a>코드
[!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>참고자료
[보안 투명 코드, 수준 2](/dotnet/framework/misc/security-transparent-code-level-2)