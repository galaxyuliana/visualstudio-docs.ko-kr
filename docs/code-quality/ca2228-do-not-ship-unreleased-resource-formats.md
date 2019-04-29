---
title: 'CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4355db8b15a3869e785589170bec3f80e8f08fbb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541720"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마세요.

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 리소스 파일을 현재 지원 되지 않는.NET Framework의 버전을 사용 하 여 만들어졌습니다.

## <a name="rule-description"></a>규칙 설명
 .NET Framework의 시험판 버전을 사용 하 여 빌드된 리소스 파일은 지원 되는 버전의.NET Framework에서 사용 하지 못할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 지원 되는.NET Framework 버전을 사용 하 여 리소스를 작성 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.
