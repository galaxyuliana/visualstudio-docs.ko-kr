---
title: 'CA2137: 투명 메서드에는 확인할 수 있는 IL만 포함되어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98b75a9f67a24fd8bea1ecc3a8782b6bd9e6b34b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920603"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: 투명 메서드에는 확인할 수 있는 IL만 포함되어야 합니다.

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
메서드가 확인할 수 없는 코드를 포함하거나 형식을 참조로 반환합니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 보안 투명 코드에서 확인할 수 없는 MSIL(Microsoft Intermediate Language)을 실행하려고 할 때 적용됩니다. 그러나 이 규칙은 완전한 IL 검증 도구를 포함하지 않으며 대신 추론을 사용하여 MSIL 확인 시 대부분의 위반을 catch합니다.

코드에 안정형 MSIL만 포함 되어 있는지 확인 하려면 어셈블리에서 [peverify (Peverify 도구)](/dotnet/framework/tools/peverify-exe-peverify-tool) 를 실행 합니다. 오류를 발생 시키는 확인할 수 없는 투명 메서드만으로 출력을 제한 하는/huioption을 사용 하 여 PEVerify를 실행 합니다. /Suia 옵션을 사용 하지 않는 경우 PEVerify는 비안정형 코드를 포함할 수 있는 중요 한 메서드를 확인 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 메서드를 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 하거나 확인할 수 없는 코드를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
이 예제의 메서드는 비안정형 코드를 사용 하며 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 되어야 합니다.

[!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]