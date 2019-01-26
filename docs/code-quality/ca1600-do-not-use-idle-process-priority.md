---
title: 'CA1600: 유휴 프로세스 우선 순위를 사용하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9eb25ace4ee255348f616abefcccd84713715ff
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037527"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: 유휴 프로세스 우선 순위를 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|범주|Microsoft.Mobility|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 이 규칙은 프로세스 설정 된 경우 `ProcessPriorityClass.Idle`합니다.

## <a name="rule-description"></a>규칙 설명
 프로세스 우선 순위를 유휴 상태로 설정하지 마십시오. 프로세스를 `System.Diagnostics.ProcessPriorityClass.Idle` 유휴, 고 블록이 대기 하는 경우에 CPU를 차지 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 프로세스로 `ProcessPriorityClass.BelowNormal`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 유휴 프로세스 우선 순위 필수 항목이 며 이동성 고려 사항을 안전 하 게 무시할 수 있습니다 하는 경우에이 규칙을 표시 하지 않습니다.