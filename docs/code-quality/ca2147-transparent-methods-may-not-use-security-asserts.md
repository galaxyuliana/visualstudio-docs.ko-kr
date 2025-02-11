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
ms.openlocfilehash: e1b56001f5a083317911edde9282b66758deb1b6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920720"
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.

|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
로 <xref:System.Security.SecurityTransparentAttribute> 표시 된 코드에 어설션할 수 있는 권한이 부여 되지 않았습니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 100% 투명 하거나 투명/중요 혼합 어셈블리의 모든 메서드와 형식을 분석 하 고의 <xref:System.Security.CodeAccessPermission.Assert%2A>선언적 또는 명령적 사용에 플래그를 사용 합니다.

런타임에 투명 코드에서를 <xref:System.Security.CodeAccessPermission.Assert%2A> 호출 하면이 <xref:System.InvalidOperationException> throw 됩니다. 이 문제는 100% 투명 어셈블리 및 메서드나 형식이 투명 하 게 선언 되었지만 선언적 또는 명령적 어설션이 포함 된 투명/중요 한 어셈블리 혼합에서 발생할 수 있습니다.

.NET Framework 2.0에는 *투명도*라는 기능이 도입 되었습니다. 개별 메서드, 필드, 인터페이스, 클래스 및 형식은 투명 하거나 중요할 수 있습니다.

투명 코드는 보안 권한을 상승 시킬 수 없습니다. 따라서이에 부여 되거나 요청 된 모든 권한은 코드를 통해 호출자 또는 호스트 응용 프로그램 도메인에 자동으로 전달 됩니다. 권한 상승의 예로는 assert, LinkDemands, SuppressUnmanagedCode 및 `unsafe` code가 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 문제를 해결 하려면 assert를 호출 하는 코드를로 <xref:System.Security.SecurityCriticalAttribute>표시 하거나 어설션을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서 메시지를 표시 하지 마십시오.

## <a name="example"></a>예제
`Assert` 메서드가 `SecurityTestClass` 을<xref:System.InvalidOperationException>throw 할 때이 투명 하 게 되 면이 코드는 실패 합니다.

[!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>예제
한 가지 옵션은 아래 예제에서 SecurityTransparentMethod 메서드를 코드 검토 하는 것이 고, 메서드가 권한 상승을 위해 안전한 것으로 간주 되는 경우 SecurityTransparentMethod를 보안 위험으로 표시 하는 것입니다. 이렇게 하려면 Assert에서 메서드 내에서 발생 하는 모든 호출에 대해 세부적인 전체 및 오류 없는 보안 감사를 수행 해야 합니다.

[!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

또 다른 옵션은 코드에서 어설션을 제거 하 고 모든 후속 파일 i/o 권한 요구가 호출자에 게 SecurityTransparentMethod 이상 전달 되도록 하는 것입니다. 이렇게 하면 보안 검사를 수행할 수 있습니다. 이 경우 권한 요구가 호출자 및/또는 응용 프로그램 도메인으로 전달 되기 때문에 보안 감사가 필요 하지 않습니다. 권한 요청은 보안 정책, 호스팅 환경 및 코드 소스 권한 부여를 통해 긴밀 하 게 제어 됩니다.

## <a name="see-also"></a>참고자료
[보안 경고](../code-quality/security-warnings.md)