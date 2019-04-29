---
title: 'CA2123: 재정의 링크 요청은 기본 링크 요청과 같아야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 52959279bca5aa0f86722050f6118f64997a901d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545054"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: 재정의 링크 요청은 기본 링크 요청과 같아야 합니다.

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 공용 형식에서 public 또는 protected 메서드는 인터페이스를 구현 및 동일한 수 없는 메서드를 재정의 [링크 요구가](/dotnet/framework/misc/link-demands) 인터페이스 또는 가상 메서드.

## <a name="rule-description"></a>규칙 설명
 이 규칙에서는 메서드를 다른 형식의 인터페이스이거나 가상 메서드인 기본 메서드에 일치시킨 다음 각각에 대해 링크 요청을 비교합니다. 메서드 또는 기본 메서드가 링크 요청이 있는 경우 하지 않으면 위반이 보고 됩니다.

 이 규칙을 위반 하는 경우 악의적인 호출자가 보안 되지 않은 메서드를 호출 하 여 링크 요청을 무시할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 재정의 메서드를 구현 하려면 동일한 링크 요청을 적용 합니다. 없는 경우 전체 요청을 사용 하 여 메서드를 표시 하거나 특성을 완전히 제거 하십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 다양 한이 규칙 위반을 보여 줍니다.

 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [링크 요청](/dotnet/framework/misc/link-demands)