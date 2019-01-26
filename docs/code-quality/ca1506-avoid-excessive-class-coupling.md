---
title: 'CA1506: 클래스를 지나치게 많이 결합하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a359df7f9538c1b1bc3fe03f1f711a41adca009e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931247"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: 클래스를 지나치게 많이 결합하지 마세요.

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|범주|Microsoft.Maintainability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식 또는 메서드를 여러 가지 결합 됩니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 형식 또는 메서드에 들어 있는 고유한 형식 참조의 개수를 계산하여 클래스 결합을 측정합니다.

 형식과 메서드를 클래스 결합 수준이 높은 유지 관리 하기 어려울 수 있습니다. 형식 및 메서드가 낮은 결합 및 높은 응집력은 서로를 보는 것이 좋습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 위반을 해결 하려면 형식 또는 메서드는 결합 된 형식의 수를 줄이기 위해를 다시 디자인 해 보십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 형식 또는 메서드가 크더라도 아직 많은 다른 형식에 대 한 종속성에도 불구 하 고 하는 경우이 경고를 제외 합니다.

## <a name="see-also"></a>참고자료

- [유지 관리 경고](../code-quality/maintainability-warnings.md)
- [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/code-metrics-values.md)