---
title: 'CA2211: 비상수 필드는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: ff103936f815f369bb66b54efc379306b52b8375
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036357"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: 비상수 필드는 노출되면 안 됩니다.

|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|범주|Microsoft.Usage|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 정적 필드 상수 되지 않으며 읽기 전용입니다.

## <a name="rule-description"></a>규칙 설명
 상수도 아니고 읽기 전용도 아닌 정적 필드는 스레드로부터 안전하지 않습니다. 이러한 필드에 대 한 액세스 신중 하 게 제어 해야 하며 클래스 개체에 대 한 액세스를 동기화 하는 것에 대 한 고급 프로그래밍 기술입니다. 이 어려운 기술에 알아보려면 이므로 이러한 개체를 테스트 자체 문제를 제기 정적 필드 변경 되지 않는 데이터를 저장할 가장 사용 됩니다. 라이브러리;에이 규칙이 적용 됩니다. 응용 프로그램은 모든 필드를 노출 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 상수 또는 읽기 전용 정적 필드를 확인 합니다. 없는 경우에 스레드로부터 안전한 내부 필드에 대 한 액세스를 관리 하는 스레드로부터 안전한 속성과 같은 대체 메커니즘을 사용 하 여 형식 다시 디자인 합니다. 성능 및 라이브러리의 동작은 잠금 경합 및 교착 상태와 같은 문제는 영향을 실현 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 응용 프로그램을 개발 하는 경우이 규칙에서 경고를 표시 하 여 정적 필드를 포함 하는 형식에 대 한 액세스를 완전히 제어할 했으므로 안전 합니다. 라이브러리 디자이너가;이 규칙에서 경고를 표시 해야 상수가 아닌 정적 필드를 사용 하 여 올바르게 사용 하도록 개발자를 위한 어려울 라이브러리를 사용 가능 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]