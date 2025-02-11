---
title: 'CA2136: 멤버는 충돌하는 투명도 주석을 포함할 수 없습니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1dcef8fbfd61b8cd8c946f76d6fcb93dc46f1654
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920624"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: 멤버는 충돌하는 투명도 주석을 포함할 수 없습니다.

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
이 규칙은 형식 멤버가 멤버 컨테이너의 보안 특성과 다른 <xref:System.Security> 투명도를 갖는 보안 특성으로 표시 될 때 발생 합니다.

## <a name="rule-description"></a>규칙 설명
투명성 특성은 큰 범위의 코드 요소에서 작은 범위의 요소에 적용됩니다. 범위가 큰 코드 요소의 투명성 특성은 첫 번째 요소에 포함된 코드 요소의 투명성 특성보다 우선합니다. 예를 들어 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 된 클래스에는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 된 메서드가 포함 될 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 위반 문제를 해결 하려면 범위가 낮은 코드 요소에서 보안 특성을 제거 하거나 해당 특성을 포함 하는 코드 요소와 동일 하 게 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서 경고를 표시 하지 않습니다.

## <a name="example"></a>예제
다음 예제에서 메서드는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 되며, <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 된 클래스의 멤버입니다. 보안 안전 특성을 제거 해야 합니다.

[!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]