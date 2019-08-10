---
title: 'CA1821: 빈 종료자를 제거하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c8c4d4ca04c7a9a21cd1e80e4dc06e8d5a92c2f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921369"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: 빈 종료자를 제거하십시오.

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|범주|Microsoft.Performance|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
형식은 비어 있거나 기본 형식 종료자만 호출 하거나 조건부로 내보낸 메서드만 호출 하는 종료자를 구현 합니다.

## <a name="rule-description"></a>규칙 설명
개체 수명을 추적할 때에는 추가로 성능 오버헤드가 발생하므로 가능한 경우 종료자를 사용하지 마십시오. 가비지 수집기는 개체를 수집 하기 전에 종료자를 실행 합니다. 즉, 두 컬렉션은 개체를 수집 해야 합니다. 빈 종료자를 사용 하면 어떠한 이점도 없이 오버 헤드가 추가 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
빈 종료자를 제거 합니다. 디버깅에 종료자가 필요한 경우 전체 종료자를 지시문으로 `#if DEBUG / #endif` 묶습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서 메시지를 표시 하지 마십시오. 종료를 표시 하지 않으면 성능이 저하 되 고 아무런 이점도 제공 되지 않습니다.

## <a name="example"></a>예제
다음 예제에서는 제거 해야 하는 빈 종료자, 지시문에 `#if DEBUG / #endif` 포함 되어야 하는 종료자 및 `#if DEBUG / #endif` 지시문을 올바르게 사용 하는 종료자를 보여 줍니다.

[!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]