---
title: 'CA1504: 잘못된 필드 이름을 검토하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da99bab4235028f75146be1807162e93759d3eb9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54926464"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: 잘못된 필드 이름을 검토하세요.

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|범주|Microsoft.Maintainability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 인스턴스 필드의 이름이 "s_" 또는 이름으로 시작 된 `static` (`Shared` 에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 필드 "m_"로 시작 합니다.

## <a name="rule-description"></a>규칙 설명
 필드 이름은 "s_"로 시작 하는 많은 사용자가 정적 데이터를 사용 하 여 연결 됩니다. 마찬가지로, "m_"로 시작 하는 필드 이름은 (멤버) 인스턴스 데이터와 연결 됩니다. 쉽고 유지 관리 코드에 대 한 이름을 일반적으로 사용 되는 규칙을 따라야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적절 한 접두사를 사용 하 여 필드를 이름을 바꿉니다. 또는 추가 하거나 제거 하 여 현재 접미사를 사용 하 여 필드를 확인 합니다 `static` 한정자입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.