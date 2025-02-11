---
title: 'CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b3c3fe41332d488d180ddafbedfe29da1a3855e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921782"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마세요.

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|범주|Microsoft.Mobility|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
타이머의 간격이 초당 두 번 이상 발생 하도록 설정 되어 있습니다.

## <a name="rule-description"></a>규칙 설명
초당 한 번 이상 폴링 하지 마십시오. 또는 초당 두 번 이상 발생 하는 타이머를 사용 합니다. 정기적인 작업의 실행 빈도가 높아지면 CPU 사용률도 높아져 디스플레이 및 하드 디스크를 끄는 절전 유휴 타이머에 방해가 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
타이머 간격을 초당 한 번 미만으로 설정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
타이머를 초당 두 번 이상 실행 해야 하며 이동성 고려 사항은 안전 하 게 무시할 수 있는 경우에만이 규칙을 무시 해야 합니다.