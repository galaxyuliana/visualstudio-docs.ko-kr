---
title: 'CA2107: deny 및 permit only 사용을 검토하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2107
- ReviewDenyAndPermitOnlyUsage
helpviewer_keywords:
- ReviewDenyAndPermitOnlyUsage
- CA2107
ms.assetid: 366f4a56-ae93-4882-81d0-bd0a55ebbc26
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c251b9fbf8327369acf20ef6acea0518e2b16913
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808265"
---
# <a name="ca2107-review-deny-and-permit-only-usage"></a>CA2107: deny 및 permit only 사용을 검토하세요.

|||
|-|-|
|TypeName|ReviewDenyAndPermitOnlyUsage|
|CheckId|CA2107|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 메서드는 PermitOnly 또는 Deny 보안 동작을 지정 하는 보안 검사를 포함 합니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName> .NET Framework 보안 잘된 알고 있는 사용자에 의해서만 보안 동작을 사용 해야 합니다. 이러한 보안 동작을 사용하는 코드는 보안 검토를 거쳐야 합니다.

 거부 하는 보안 요청에 대 한 응답에서 발생 하는 스택 워크의 기본 동작을 변경 합니다. 거부 메서드를 호출 스택에 있는 호출자의 실제 권한과 관계 없이 기간에 대 한 부여 되지 않아야 하는 권한을 지정할 수 있습니다. 스택 워크 Deny로 보호 되는 메서드를 검색 하 고 요청 된 권한이 거부 된 권한에 포함 되어, 경우 스택 워크가 실패 합니다. 또한 PermitOnly 스택 워크의 기본 동작을 변경합니다. 코드를에서 호출자의 권한과 관계 없이 부여할 수 있는 권한만 지정할 수 있습니다. 스택 워크 PermitOnly에서 보호 되는 메서드를 검색 하 고는 PermitOnly 하 여 지정 된 사용 권한에서 요청 된 권한이 포함 되지 않으면, 스택 워크가 실패 합니다.

 제한 된 유용성 및 동작이 약간 보안 취약점에 대 한 이러한 작업에 사용 하는 코드를 신중 하 게 평가 되어야 합니다. 다음을 살펴보세요.

- [링크 요청](/dotnet/framework/misc/link-demands) Deny 또는 PermitOnly 영향을 받지 않습니다.

- Deny 또는 PermitOnly 스택 워크는 요청과 동일한 스택 프레임의 경우 보안 동작을 아무런 효과가 없습니다.

- 일반적으로 여러 가지 방법으로 경로 기반 권한을 구성 하는 데 사용 되는 값을 지정할 수 있습니다. 한 가지 형태의 경로에 대 한 액세스를 거부 하 여 모든 형태의 액세스를 거부 하지 않는 합니다. 예를 들어, 파일 공유 \\거부 해야 \Server\Share 네트워크 공유에서 파일에 대 한 액세스를 거부 하려면 x: 드라이브에 매핑되어 \\\Server\Share\File, X:\File, 및 파일에 액세스 하는 다른 모든 경로입니다.

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> Deny 또는 PermitOnly에 도달 하기 전에 스택 워크를 종료할 수 있습니다.

- Deny가 적용 하는 경우 즉, 호출자에 게 Deny에 의해 차단 된 권한이 호출자에 게 액세스할 수 있습니다 보호 되는 리소스를 직접 Deny 무시. 마찬가지로, 호출자에 게 권한이 없으면 스택 워크를 거부 하지 않고 실패 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이러한 보안 동작을 사용 하면 위반이 발생 합니다. 위반을 해결 하려면 이러한 보안 동작을 사용 하지 마십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 보안 검토를 완료 한 후에이 규칙에서 경고를 표시 합니다.

## <a name="example-1"></a>예제 1
 다음 예제에서는 거부의 몇 가지 제한 사항이 있습니다.

 다음 라이브러리를 보호 하는 보안 요구를 제외 하 고 동일한 두 메서드가 포함 된 클래스를 포함 합니다.

 [!code-csharp[FxCop.Security.PermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_1.cs)]

## <a name="example-2"></a>예제 2
 다음 응용 프로그램 라이브러리에서 보안 방법 거부의 효과 보여 줍니다.

 [!code-csharp[FxCop.Security.TestPermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Demand: Caller's Deny has no effect on Demand with the asserted permission.
LinkDemand: Caller's Deny has no effect on LinkDemand with the asserted permission.
LinkDemand: Caller's Deny has no effect with LinkDemand-protected code.
LinkDemand: This Deny has no effect with LinkDemand-protected code.
```

## <a name="see-also"></a>참고자료

- <xref:System.Security.CodeAccessPermission.PermitOnly%2A?displayProperty=fullName>
- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName>
- <xref:System.Security.IStackWalk.PermitOnly%2A?displayProperty=fullName>
- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)