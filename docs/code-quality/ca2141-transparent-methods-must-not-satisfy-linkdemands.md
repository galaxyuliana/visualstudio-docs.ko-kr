---
title: 'CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59b8c01f6e542093268c31d1edaf29d690aa6c5e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54926504"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다

|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 로 표시 되지 않은 어셈블리의 메서드를 호출 하는 보안 투명 메서드가 합니다 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 특성 또는 보안 투명 메서드가 충족을 <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` 형식 또는 메서드에 대 한 합니다.

## <a name="rule-description"></a>규칙 설명
 LinkDemand를 충족 하는 것은 의도 하지 않은 권한 상승 시킬 수 있는 보안 중요 한 작업입니다. 보안 투명 코드 보안상 중요 한 코드와 같은 보안 감사 요구 사항이 적용 되지 않으므로 LinkDemands를 충족 하지 해야 합니다. 보안 규칙 집합 수준 1 어셈블리의 투명 한 메서드는 런타임에 성능 문제를 일으킬 수 있는 전체 요청을 변환할 수를 충족 하는 모든 LinkDemands를 발생 합니다. 보안 규칙 집합 수준 2 어셈블리에서 투명 한 메서드는 LinkDemand를 충족 하려고 하면 적시에 (JIT) 컴파일러에 컴파일할 수 없게 됩니다.

 수준 2 보안을 사용 하는 어셈블리, 보안 투명 메서드가 충족 시키거나-APTCA 어셈블리의 메서드를 호출 하는 시도 발생 시킵니다는 <xref:System.MethodAccessException>; 수준 1 어셈블리의 LinkDemand 전체 요청이 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 액세스 메서드를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 또는 액세스 메서드에서 LinkDemand를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 이 예제에서는 투명 메서드는 LinkDemand를 가진 메서드를 호출 하려고 합니다. 이 규칙은이 코드에서 발생 합니다.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]