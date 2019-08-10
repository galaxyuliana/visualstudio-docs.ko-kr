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
ms.openlocfilehash: f734d0cf28a5aec28ebbf635dd384efe176b1774
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921313"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: 값 형식 필드는 이식 가능해야 합니다.

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|범주|Microsoft 이식성|
|변경 수준|중단-필드를 어셈블리 외부에서 볼 수 있는 경우입니다.<br /><br /> 분리 안 함-필드가 어셈블리 외부에 표시 되지 않는 경우|

## <a name="cause"></a>원인
이 규칙은 명시적 레이아웃으로 선언 된 구조체가 64 비트 운영 체제에서 비관리 코드로 마샬링될 때 올바르게 정렬 되는지 검사 합니다. IA-64은 정렬 되지 않은 메모리 액세스를 허용 하지 않으며,이 위반이 해결 되지 않으면 프로세스가 중단 됩니다.

## <a name="rule-description"></a>규칙 설명
잘못 정렬 된 필드를 포함 하는 명시적 레이아웃이 있는 구조체는 64 비트 운영 체제에서 충돌을 일으킵니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
8 바이트 보다 작은 모든 필드는 크기의 배수이 고 8 바이트 이상인 필드는 8의 배수 오프셋을 포함 해야 합니다. 또 다른 솔루션은 적절 `LayoutKind.Sequential` 한 경우 `LayoutKind.Explicit`대신를 사용 하는 것입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
오류가 발생 하는 경우에만이 경고를 표시 하지 않아야 합니다.