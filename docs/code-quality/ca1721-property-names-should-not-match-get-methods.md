---
title: 'CA1721: 속성 이름은 Get 메서드와 달라야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 88a56a37248112d377b47054ed815a4aa2629f9d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953934"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: 속성 이름은 Get 메서드와 달라야 합니다.

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 멤버의 이름을 'Get'로 시작 하 고 그렇지 않은 경우 public 또는 protected 속성의 이름과 일치 하 합니다. 예를 들어, '메서드와' 및 '색' 이라고 하는 속성 이라고 하는 메서드가 포함 된 형식은이 규칙을 위반 합니다.

## <a name="rule-description"></a>규칙 설명
 Get 메서드 및 속성 서로 분명히 구분 하는 이름을 사용 해야 합니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이 일관성에는 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 높이고 새 소프트웨어 라이브러리 하는 데 필요한 시간이 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 'Get'를 사용 하 여 접두사가 있는 메서드 이름을 일치 하지 않으면 있도록 이름을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

> [!NOTE]
> Get 메서드 IExtenderProvider 인터페이스를 구현 하 여 발생 하는 경우이 경고를 제외할 수 있습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 속성과 메서드를 포함 합니다.

 [!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
 [!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1024: 적절 한 속성을 사용 합니다.](../code-quality/ca1024-use-properties-where-appropriate.md)