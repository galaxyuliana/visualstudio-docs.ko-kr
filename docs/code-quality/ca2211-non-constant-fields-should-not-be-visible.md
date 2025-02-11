---
title: 'CA2211: 비상수 필드는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 77909627385a7aa2e41f87c23ec41dc8ac0e1a5e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920354"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: 비상수 필드는 노출되면 안 됩니다.

|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|범주|Microsoft.Usage|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
Public 또는 protected 정적 필드가 상수가 아니거나 읽기 전용입니다.

## <a name="rule-description"></a>규칙 설명
상수도 아니고 읽기 전용도 아닌 정적 필드는 스레드로부터 안전하지 않습니다. 이러한 필드에 대 한 액세스는 신중 하 게 제어 해야 하며 클래스 개체에 대 한 액세스를 동기화 하기 위한 고급 프로그래밍 기술이 필요 합니다. 이러한 방법은 학습 및 마스터를 위한 어려운 기술 이며 이러한 개체를 테스트 하는 것은 고유한 과제를 발생 시키고, 정적 필드는 변경 되지 않는 데이터를 저장 하는 데 가장 적합 합니다. 이 규칙은 라이브러리에 적용 됩니다. 응용 프로그램은 필드를 노출 하면 안 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 정적 필드를 상수 또는 읽기 전용으로 설정 합니다. 가능 하지 않은 경우 기본 필드에 대 한 스레드로부터 안전한 액세스를 관리 하는 스레드로부터 안전한 속성과 같은 대체 메커니즘을 사용 하도록 형식을 다시 디자인 합니다. 잠금 경합 및 교착 상태와 같은 문제는 라이브러리의 성능 및 동작에 영향을 줄 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
응용 프로그램을 개발 하 고 있으므로 정적 필드를 포함 하는 형식에 대 한 모든 권한을 보유 하는 경우에는이 규칙에서 경고를 표시 하지 않아도 됩니다. 라이브러리 디자이너에서이 규칙의 경고를 표시 해서는 안 됩니다. 비상수 정적 필드를 사용 하면 개발자가 제대로 사용 하기 어렵게 라이브러리를 사용할 수 있습니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

[!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]