---
title: 'CA1822: 멤버를 static으로 표시하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f25b74949c734921c313ae2cf00a2d217029e52
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921381"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: 멤버를 static으로 표시하세요.

|||
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|범주|Microsoft.Performance|
|변경 수준|중단-변경 내용에 관계 없이 멤버가 어셈블리 외부에 표시 되지 않는 경우입니다. 중단 하지 않음- `this` 키워드를 사용 하 여 멤버를 인스턴스 멤버로 변경 하는 경우에만 해당 됩니다.<br /><br /> 중단-멤버를 인스턴스 멤버에서 정적 멤버로 변경 하 고 어셈블리 외부에서 볼 수 있는 경우.|

## <a name="cause"></a>원인
인스턴스 데이터에 액세스 하지 않는 멤버는 static으로 표시 되지 않습니다 (에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]공유).

## <a name="rule-description"></a>규칙 설명
인스턴스 데이터에 액세스하지 않거나 인스턴스 메서드를 호출하지 않는 멤버는 static([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Shared)으로 표시할 수 있습니다. 메서드를 static으로 표시하면 컴파일러는 이러한 멤버에 대한 비가상 호출 사이트를 내보냅니다. 비가상 호출 사이트를 내보내면 현재 개체 포인터가 null이 아닌지 확인 하는 각 호출에 대해 런타임에 검사를 수행 하지 못합니다. 이렇게 하면 성능이 중요 한 코드의 성능을 향상 시킬 수 있습니다. 경우에 따라 현재 개체 인스턴스에 액세스 하지 못하는 경우 정확성 문제가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
멤버를 static으로 표시 하거나에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]공유 하거나, 해당 하는 경우 메서드 본문에서 ' this '/' Me '를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이전에 제공 된 코드에 대 한 경고를 수정 하 여 주요 변경 내용을 적용할 수 있는 것은 안전 합니다.

## <a name="related-rules"></a>관련 규칙
[CA1811: 호출 되지 않는 private 코드 방지](../code-quality/ca1811-avoid-uncalled-private-code.md)

[CA1812: 인스턴스화되지 않은 내부 클래스를 사용 하지 마십시오.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1804: 사용 하지 않는 지역 제거](../code-quality/ca1804-remove-unused-locals.md)