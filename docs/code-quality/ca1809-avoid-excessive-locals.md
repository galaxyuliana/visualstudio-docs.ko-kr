---
title: 'CA1809: 불필요한 로컬 항목을 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d1c2f76258be3b0be6409bffd002fd916883ab2
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921544"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: 불필요한 로컬 항목을 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|범주|Microsoft.Performance|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
멤버에 64 개 이상의 지역 변수가 포함 되어 있으며, 그 중 일부는 컴파일러에서 생성 될 수 있습니다.

## <a name="rule-description"></a>규칙 설명
일반적인 성능 최적화는 값을 *등록* 하는 것이 아니라 프로세서 레지스터의 값을 메모리에 저장 하는 것입니다. 공용 언어 런타임은 enregistration에 대해 최대 64 지역 변수를 고려 합니다. 레지스터 되지 않은 변수는 스택에 배치 되며 조작 전에 레지스터로 이동 해야 합니다. 모든 지역 변수가 레지스터 될 가능성을 허용 하려면 지역 변수 수를 64으로 제한 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 64 개 미만의 지역 변수를 사용 하도록 구현을 리팩터링 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
성능에 문제가 없는 경우에는이 규칙에서 경고를 표시 하지 않거나 규칙을 사용 하지 않도록 설정 하는 것이 안전 합니다.

## <a name="related-rules"></a>관련 규칙
[CA1804: 사용 하지 않는 지역 제거](../code-quality/ca1804-remove-unused-locals.md)