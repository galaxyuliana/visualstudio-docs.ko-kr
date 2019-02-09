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
ms.openlocfilehash: 03948506d928f7d638b21c1fa4bc0a35818ec09a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926916"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

사용 하 여 어셈블리의 메서드는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 특성 특성이 없는 어셈블리에서 메서드를 호출 합니다.

## <a name="rule-description"></a>규칙 설명

기본적으로 강력한 이름의 어셈블리에서 public 또는 protected 메서드는 암시적으로 보호 된 여는 [링크 요구가](/dotnet/framework/misc/link-demands) 완전 신뢰에만 완전히 신뢰할 수 있는 호출자에 게는 강력한 이름의 어셈블리에 액세스할 수 있습니다. 강력한 이름의 어셈블리는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA)이이 보호를 권한이 없습니다. 특성 사용 어셈블리와 같은 인터넷 또는 인트라넷에서 실행 되는 코드가 완전히 신뢰 되지 않은 호출자에 게 액세스할 수 있게 하는 링크 요청 하지 않도록 설정 합니다.

APTCA 특성은 완전히 신뢰할 수 있는 어셈블리에 부분적으로 신뢰할 수 있는 호출자를 허용 하지 않는 다른 어셈블리의 코드를 실행 하는 경우 보안상 위험할 가능성이 있습니다. 경우 두 가지 방법 `M1` 하 고 `M2` 다음 조건을 충족, 악의적인 호출자는 메서드를 사용할 수 있습니다 `M1` 보호 하는 완전 신뢰 암시적 링크 요청을 무시 하도록 `M2`:

- `M1` 공용 메서드는 APTCA 특성이 있는 완전 신뢰 어셈블리에 선언 됩니다.

- `M1` 메서드를 호출 `M2` 외부 `M1`의 어셈블리입니다.

- `M2`어셈블리에 APTCA 특성이 없고, 따라서 실행 하지 않아야 하거나 부분적으로 신뢰할 수 있는 호출자를 대신 하 여 합니다.

부분적으로 신뢰할 수 있는 호출자 `X` 메서드를 호출할 수 있습니다 `M1`발생 `M1` 호출할 `M2`합니다. 때문에 `M2` APTCA 특성을 직접 호출자 없는 (`M1`) 완전 신뢰에 대 한 링크 요청을 충족 해야 합니다 `M1` 완전 신뢰가 있고 따라서이 검사를 충족 합니다. 보안 위험을 이므로 `X` 만족 보호 하는 링크 요청에 참여 하지 않는 `M2` 신뢰할 수 없는 호출자에서. 따라서 메서드는 APTCA 특성으로 메서드를 호출 해서는 특성이 없는 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 APCTA 특성이 필요한 경우 완전 신뢰 어셈블리를 호출 하는 메서드를 보호 하기 위해 요청을 사용 합니다. 정확한 권한을 요구에 메서드로 노출 하는 기능에 따라 달라 집니다. 가능한 경우 기본 기능을 부분적으로 신뢰할 수 있는 호출자에 게 노출 되지 않도록 하려면 완전 신뢰에 대 한 요청을 사용 하 여 메서드를 보호 합니다. 없는 경우에 노출 된 기능을 효과적으로 보호 하는 사용 권한 집합을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서 경고를 안전 하 게 표시 하지 않으려면 메서드에서 노출 하는 기능을 허용 하지 않도록 직접 또는 간접적으로 호출자가 중요 한 정보, 작업 또는 안전 하지 않은 방식으로 사용할 수 있는 리소스에 액세스 하도록 해야 합니다.

## <a name="example-1"></a>예제 1
 다음 예제에서는이 규칙에서 검색 하는 보안 문제를 설명 하기 위해 두 명의 어셈블리 및 테스트 응용 프로그램을 사용 합니다. 첫 번째 어셈블리에 APTCA 특성 없고 부분적으로 신뢰할 수 있는 호출자에 게 액세스할 수 없습니다 (나타내는 `M2` 이전 토론에서).

 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>예제 2
 두 번째 어셈블리를 완전히 신뢰할 수 있는 하 여 부분적으로 신뢰할 수 있는 호출자 허용 (나타내는 `M1` 이전 토론에서).

 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>예제 3
 테스트 응용 프로그램 (나타내는 `X` 이전 토론에서) 부분적으로 신뢰할 수 있습니다.

 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>관련된 규칙

- [CA2117: APTCA 형식은 APTCA 기본 형식만 확장 해야](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)