---
title: 'CA1415: P/Invoke를 올바르게 선언하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da6448a414437a07b545a999b35031f82e9a8689
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936878"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: P/Invoke를 올바르게 선언하십시오.

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경 아님-매개 변수를 선언 하는 P/Invoke 어셈블리 외부에 노출 되지 않는 경우 주요-매개 변수를 선언 하는 P/Invoke 어셈블리 외부에서 볼 수 있는 경우입니다.|

## <a name="cause"></a>원인
 플랫폼 호출 메서드 잘못 선언 되었습니다.

## <a name="rule-description"></a>규칙 설명
 플랫폼 메서드가 관리 되지 않는 코드에 액세스를 호출 하 고 사용 하 여 정의 되는 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. 플랫폼 호출 메서드 선언을 OVERLAPPED 구조체 매개 변수에 대 한 포인터가 있는 Win32 함수를 대상으로 하는 아니며 해당 관리 되는 매개 변수에 대 한 포인터에 대 한이 규칙의에서는 현재는 <xref:System.Threading.NativeOverlapped?displayProperty=fullName> 구조입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 플랫폼 제대로 선언 메서드를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 플랫폼 규칙을 위반 하 고 규칙을 충족 하는 메서드를 호출 합니다.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>참고자료
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)