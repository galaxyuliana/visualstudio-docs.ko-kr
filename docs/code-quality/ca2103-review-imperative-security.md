---
title: 'CA2103: 명령적 보안을 검토하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7acbb9d0127dd2ddb6668e72db8fa88124ec2b3c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921424"
---
# <a name="ca2103-review-imperative-security"></a>CA2103: 명령적 보안을 검토하세요.

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
메서드가 명령적 보안을 사용하고, 요청이 활성 상태인 동안 변경될 수 있는 반환 값 또는 상태 정보를 사용하여 권한을 구성하고 있습니다.

## <a name="rule-description"></a>규칙 설명
명령적 보안은 특성을 사용 하 여 메타 데이터에 권한 및 작업을 저장 하는 선언적 보안과 비교 하 여 코드를 실행 하는 동안 사용 권한 및 보안 동작을 지정 합니다. 명령적 보안은 사용 권한 개체의 상태를 설정 하 고 런타임까지 사용할 수 없는 정보를 사용 하 여 보안 작업을 선택할 수 있기 때문에 매우 유연 합니다. 이러한 유연성과 함께 작업을 적용 하는 동안 사용 권한 상태를 확인 하는 데 사용 하는 런타임 정보가 변경 되지 않은 상태로 유지 될 위험이 있습니다.

가능하면 선언적 보안을 사용합니다. 선언적 요구는 더 쉽게 이해할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
권한 상태가 사용 되는 동안 변경 될 수 있는 정보에 의존 하지 않도록 명령적 보안 요구 사항을 검토 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
사용 권한이 변경 데이터에 의존 하지 않는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다. 그러나 명령적 수요를 선언적으로 변경 하는 것이 좋습니다.

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [데이터 및 모델링](/dotnet/framework/data/index)