---
title: 'CA2145: 투명 메서드는 SuppressUnmanagedCodeSecurityAttribute 특성으로 데코레이팅할 수 없습니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ba7926f04f6112b28770110614fa18be88b028a2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018165"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: 투명 메서드는 SuppressUnmanagedCodeSecurityAttribute 특성으로 데코레이팅할 수 없습니다.

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

투명 한 메서드를 사용 하 여 표시 된 메서드를 <xref:System.Security.SecuritySafeCriticalAttribute> 메서드 또는 메서드를 포함 하는 형식으로 표시 됩니다는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성입니다.

## <a name="rule-description"></a>규칙 설명

메서드에 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성 암시적 LinkDemand가 호출 하는 메서드에 배치 했습니다. 이 LinkDemand는 호출 코드가 보안을 중요시 하도록 요구합니다. 사용 하 여 SuppressUnmanagedCodeSecurity를 사용 하는 메서드를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 특성을 사용 하면이 요구 사항을 보다 명확 하 게 메서드의 호출자에 대 한 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 메서드를 표시 하거나 사용 하 여 입력 된 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

### <a name="code"></a>코드

[!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]