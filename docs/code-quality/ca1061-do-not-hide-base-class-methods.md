---
title: 'CA1061: 기본 클래스 메서드를 숨기지 마십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f13ac29028472384cfadbf9c397e578f6509670
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922420"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: 기본 클래스 메서드를 숨기지 마십시오.

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
파생 된 형식은 기본 메서드 중 하 나와 동일한 수의 매개 변수를 사용 하 여 동일한 이름을 가진 메서드를 선언 합니다. 하나 이상의 매개 변수는 기본 메서드에서 해당 하는 매개 변수의 기본 형식입니다. 그리고 나머지 모든 매개 변수에는 기본 메서드의 해당 매개 변수와 동일한 형식이 있습니다.

## <a name="rule-description"></a>규칙 설명
파생 된 메서드의 매개 변수 시그니처가 기본 메서드의 매개 변수 시그니처에 있는 해당 형식 보다 더 약하게 파생 된 형식에 의해서만 다른 경우 기본 형식의 메서드는 파생 된 형식에서 동일한 이름의 메서드에 의해 숨겨집니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 메서드를 제거 하거나 이름을 변경 하거나 메서드가 기본 메서드를 숨기지 않도록 매개 변수 서명을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 메서드를 보여 줍니다.

[!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]