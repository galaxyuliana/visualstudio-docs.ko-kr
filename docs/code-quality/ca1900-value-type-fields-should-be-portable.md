---
title: 'CA1900: 값 형식 필드는 이식 가능해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e823a58d7a2be45c43305320bd32175de7a3fad6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953726"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: 값 형식 필드는 이식 가능해야 합니다.

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|범주|Microsoft.Portability|
|변경 수준|주요-어셈블리 외부의 필드를 볼 수 있는 경우입니다.<br /><br /> 주요 변경 아님-필드 어셈블리 외부에서 볼 수 없는 경우|

## <a name="cause"></a>원인
 이 규칙은 명시적 레이아웃을 사용 하 여 선언 된 구조체가 64 비트 운영 체제에서 비관리 코드로 마샬링될 때 올바르게 맞춰지는지 검사 합니다. IA-64 정렬 되지 않은 메모리에 액세스 하 고이 위반을 수정 하지 않으면 프로세스 충돌 허용 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 64 비트 운영 체제에서 충돌 불일치 필드를 포함 하는 명시적 레이아웃이 있는 구조체입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 8 바이트 보다 작은 모든 필드는 해당 크기의 배수에 오프셋 및 필드는 8 바이트에 있어야 합니다. 또는 더 8의 배수가 되는 오프셋 있어야 합니다. 다른 솔루션을 사용 하는 것 `LayoutKind.Sequential` 대신 `LayoutKind.Explicit`적절 한 경우.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 오류가 발생 하는 경우에이 경고를 표시 하지 않습니다.