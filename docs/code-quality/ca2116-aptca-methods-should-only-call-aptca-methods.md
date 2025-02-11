---
title: 'CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f55c48583e47a4602f33d69799d1d86a6c9c3e56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921150"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

<xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 특성을 사용 하는 어셈블리의 메서드가 특성을 포함 하지 않는 어셈블리의 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명

기본적으로 강력한 이름의 어셈블리에서 public 또는 protected 메서드는 완전 신뢰에 대 한 [링크 요청](/dotnet/framework/misc/link-demands) 에 의해 암시적으로 보호 됩니다. 완전히 신뢰할 수 있는 호출자만 강력한 이름의 어셈블리에 액세스할 수 있습니다. <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 특성으로 표시 된 강력한 이름의 어셈블리에는이 보호가 포함 되지 않습니다. 특성은 링크 요청을 사용 하지 않도록 설정 하 여 인트라넷 또는 인터넷에서 실행 되는 코드와 같이 완전 신뢰가 없는 호출자가 어셈블리에 액세스할 수 있도록 합니다.

완전히 신뢰할 수 있는 어셈블리에 APTCA 특성이 있고 어셈블리에서 부분적으로 신뢰할 수 있는 호출자를 허용 하지 않는 다른 어셈블리의 코드를 실행 하는 경우 보안을 악용할 수 있습니다. 두 가지 방법 `M1` 및 `M2` 가 다음 조건을 충족 하는 경우 악성 호출자는 메서드 `M1` 를 사용 하 여를 보호 `M2`하는 암시적 완전 신뢰 링크 요청을 무시할 수 있습니다.

- `M1`는 APTCA 특성이 있는 완전히 신뢰할 수 있는 어셈블리에 선언 된 공용 메서드입니다.

- `M1`어셈블리 외부 `M2` `M1`에서 메서드를 호출 합니다.

- `M2`의 어셈블리에 APTCA 특성이 없으므로 부분적으로 신뢰할 수 있는 호출자 대신 또는에서 실행 해서는 안 됩니다.

부분적으로 신뢰할 수 `X` 있는 호출자는 `M1`메서드 `M1` 를 호출 하 `M2`여를 호출할 수 있습니다. 에 `M2` APTCA 특성이 없으므로 해당 직계 호출자 (`M1`)는 완전 신뢰에 대 한 링크 요구를 충족 해야 합니다. `M1` 에는 완전 신뢰가 있으므로이 검사를 충족 합니다. 는 신뢰할 수 없는 호출자 `X` 로부터 보호 `M2` 하는 링크 요구를 충족 하지 않기 때문에 보안상 위험할 수 있습니다. 따라서 APTCA 특성이 있는 메서드는 특성이 없는 메서드를 호출 해서는 안 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
APCTA 특성이 필요한 경우 요청을 사용 하 여 완전 신뢰 어셈블리로를 호출 하는 메서드를 보호 합니다. 필요한 정확한 권한은 메서드에 의해 노출 되는 기능에 따라 달라 집니다. 가능 하면 완전 신뢰 요청을 통해 메서드를 보호 하 여 기본 기능이 부분적으로 신뢰할 수 있는 호출자에 게 노출 되지 않도록 합니다. 가능 하지 않은 경우 노출 된 기능을 효과적으로 보호 하는 권한 집합을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서 경고를 안전 하 게 표시 하지 않으려면 메서드에서 노출 하는 기능이 호출자에 게 직접 또는 간접적으로 호출자가 안전 하 게 사용할 수 있는 중요 한 정보, 작업 또는 리소스에 액세스할 수 없도록 해야 합니다.

## <a name="example-1"></a>예제 1
다음 예제에서는 두 개의 어셈블리와 테스트 응용 프로그램을 사용 하 여이 규칙에 의해 검색 된 보안 취약성을 보여 줍니다. 첫 번째 어셈블리에는 APTCA 특성이 없으므로 부분적으로 신뢰할 수 있는 호출자 (이전 토론 `M2` 에서 표시)에 액세스할 수 없습니다.

[!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>예제 2
두 번째 어셈블리는 완전히 신뢰할 수 있으며, 부분적으로 신뢰할 수 있는 `M1` 호출자 (이전 토론에서로 표시 됨)를 허용 합니다.

[!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>예제 3
이전 토론에서로 `X` 표시 된 테스트 응용 프로그램은 부분적으로 신뢰할 수 있습니다.

[!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>관련 규칙

- [CA2117: APTCA 형식은 APTCA 기본 형식만 확장 해야 합니다.](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)