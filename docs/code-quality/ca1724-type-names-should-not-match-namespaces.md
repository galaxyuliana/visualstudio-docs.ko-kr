---
title: 'CA1724: 형식 이름은 네임스페이스와 달라야 합니다.'
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0bd410fabbeebc05d13eaee94db79cc346881e5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989223"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: 형식 이름은 네임 스페이스를 달라 야 합니다.

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식 이름에는 하나 이상의 외부에서 표시 되는 형식에는 참조 된 네임 스페이스 이름을 일치 합니다. 이름 비교는 대/소문자입니다.

## <a name="rule-description"></a>규칙 설명

사용자가 만든 형식 이름 형식이 외부에서 볼 수 있는 참조 된 네임 스페이스의 이름을 일치 하지 해야 합니다. 이 규칙을 위반 하면 라이브러리의 유용성을 줄일 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

형식이 외부에 표시 되는 참조 된 네임 스페이스의 이름을 일치 하지는 형식의 이름을 바꾸십시오.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

새로운 개발에 알려져 있지 않습니다 시나리오 발생이 규칙에서 경고를 표시 해야 하는 위치입니다. 경고를 표시 하지 않으려면 전에 신중 하 게 하는 방법 라이브러리의 사용자 혼동을 줄 수는 일치 하는 이름별 고려해. 제공 되는 라이브러리에 대 한이 규칙에서 경고를 표시 해야 합니다.