---
title: 'CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 36ae392173a18796c53100599fbf5f5fb5997beb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55945159"
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.

|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 로 표시 된 코드 <xref:System.Security.SecurityTransparentAttribute> 어설션 하려면 충분 한 권한이 부여 되지 않은 합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 100% 투명 또는 혼합 투명/중요 하 고 선언적 이거나 명령 적인 사용 플래그를 지정 하는 어셈블리의 모든 형식과 메서드를 분석 <xref:System.Security.CodeAccessPermission.Assert%2A>합니다.

 런타임에 호출 <xref:System.Security.CodeAccessPermission.Assert%2A> transparent 코드에서 발생 합니다는 <xref:System.InvalidOperationException> throw 됩니다. 모두 100% 투명 어셈블리 및 투명/중요 혼합된 어셈블리 메서드 또는 형식에 투명 하 게 선언 하 하지만 선언적 이거나 명령 적인 어설션 포함 위치에서 발생할 수 있습니다.

 .NET Framework 2.0 이라고 하는 기능을 도입 *투명도*합니다. 개별 메서드, 필드, 인터페이스, 클래스 및 형식 투명 하거나 중요할 수 있습니다.

 투명 코드는 보안 권한을 승격할 수 없습니다. 따라서 모든 권한이 부여 되거나 요청 호출자 또는 호스트 응용 프로그램 도메인에는 코드를 통해 자동으로 전달 됩니다. 권한 상승의 예로 빌드에서만 자산, LinkDemands SuppressUnmanagedCode, 및 `unsafe` 코드입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 사용 하 여 Assert를 호출 하는 코드를 표시 하거나 문제를 해결 하려면는 <xref:System.Security.SecurityCriticalAttribute>, 어설션을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서 메시지를 표시 하지 마십시오.

## <a name="example"></a>예제
 이 코드는 경우 실패 `SecurityTestClass` 경우 투명 하 게 됩니다 합니다 `Assert` 메서드가 throw를 <xref:System.InvalidOperationException>입니다.

 [!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>예제
 한 가지 옵션은 코드 검토 아래 예제의 SecurityTransparentMethod 메서드 및 메서드는 권한 상승에 대 한 안전한 것으로 간주 됩니다을 하는 경우 보안에 중요 한를 사용 하 여 SecurityTransparentMethod 표시. 이 함께 모든 설명선 Assert 메서드 내에서 발생 하는 방법에 자세한의 완전 하 고 오류가 없는 보안 감사를 수행 해야 함을 필요 합니다.

 [!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

 다른 옵션은 코드에서 어설션을 제거 하 고 모든 후속 파일 호출자에 게 SecurityTransparentMethod 초과 되는 I/O 권한 요청 흐름을 사용 하는 것입니다. 이 보안 검사를 활성화 합니다. 이 경우 보안 감사 안 함은 되므로, 권한 요청이 응용 프로그램 도메인 및/또는 호출자에 게로 이동 합니다. 권한 요청 호스팅 환경 및 권한 부여 코드 소스 보안 정책을 통해 제어 밀접 하 게 됩니다.

## <a name="see-also"></a>참고자료
 [보안 경고](../code-quality/security-warnings.md)