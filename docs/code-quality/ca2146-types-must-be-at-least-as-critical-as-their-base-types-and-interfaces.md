---
title: 'CA2146: 형식은 기본 형식 및 인터페이스 이상으로 중요해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a70e999505bd900a7b3d89693ef4f6a1cef9de7d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920418"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: 형식은 기본 형식 및 인터페이스 이상으로 중요해야 합니다.

|||
|-|-|
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|
|CheckId|CA2146|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
투명 형식은 <xref:System.Security.SecuritySafeCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute> 또는으로 표시 된 형식에서 파생 되거나 <xref:System.Security.SecurityCriticalAttribute> ,특성으로표시된형식이특성으로표시된형식에서파생됩니다.<xref:System.Security.SecurityCriticalAttribute>

## <a name="rule-description"></a>규칙 설명
이 규칙은 파생 형식에 기본 형식 또는 구현된 인터페이스만큼 중요하지 않은 보안 투명성 특성이 있을 때 적용됩니다. 중요한 기본 형식에서 파생되거나 중요한 인터페이스를 구현할 수 있는 것은 중요한 형식뿐이고, 안전에 중요한 기본 형식에서 파생되거나 안전에 중요한 인터페이스를 구현할 수 있는 것은 중요하거나 안전에 중요한 형식뿐입니다. 수준 2 투명도에서이 규칙이 위반 되 면 파생 된 <xref:System.TypeLoadException> 형식에 대 한가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 위반 문제를 해결 하려면 파생 또는 구현 형식을 기본 형식 또는 인터페이스 만큼 중요 한 투명도 특성으로 표시 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
[!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]