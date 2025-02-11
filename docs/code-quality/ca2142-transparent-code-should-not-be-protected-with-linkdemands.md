---
title: 'CA2142: 투명 코드는 LinkDemands로 보호될 수 없습니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf5bb8320a8876582cc325ecf973c83593777193
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920506"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: 투명 코드는 LinkDemands로 보호될 수 없습니다.

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
투명 한 메서드에는 <xref:System.Security.Permissions.SecurityAction> 또는 기타 보안 요구가 필요 합니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 액세스 하는 데 LinkDemands가 필요한 투명 메서드에 대해 발생 합니다. 보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다. 투명 한 메서드는 보안 중립적 이어야 하므로 보안 결정을 내리는 것이 아닙니다. 또한 보안을 결정 하는 안전한 중요 코드는 이전에 이러한 결정을 내리는 투명 코드에 의존 하지 않아야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 투명 메서드에서 링크 요청을 제거 하거나 보안 요구와 같은 보안 검사를 <xref:System.Security.SecuritySafeCriticalAttribute> 수행 하는 경우 메서드를 특성으로 표시 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서 메서드는 메서드가 투명 하 고가 <xref:System.Security.PermissionSet> <xref:System.Security.Permissions.SecurityAction>포함 된 LinkDemand로 표시 되어 있기 때문에 메서드에서 발생 합니다.

[!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]

이 규칙에서는 경고를 표시해야 합니다.