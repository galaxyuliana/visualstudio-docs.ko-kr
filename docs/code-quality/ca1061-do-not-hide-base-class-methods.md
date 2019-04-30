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
ms.openlocfilehash: faa225178a50be080f92a728998e914025c17168
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788662"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: 기본 클래스 메서드를 숨기지 마십시오.

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 파생된 형식이 기본 메서드; 중 하나로 매개 변수 수가 같은 동일한 이름을 가진 메서드를 선언합니다. 하나 이상의 매개 변수는 기본 메서드;에서 해당 매개 변수의 기본 형식 및 해당 기본 메서드 매개 변수와 동일 나머지 매개 변수 형식이 있습니다.

## <a name="rule-description"></a>규칙 설명
 기본 형식의 메서드는 파생 된 메서드의 매개 변수 시그니처에 더 약하게 파생 된 기본 메서드의 매개 변수 시그니처에 해당 형식 보다는 형식만 다른 경우에 파생된 된 형식에서 동일 하 게 명명 된 메서드에 의해 숨겨집니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드를 제거 또는 바꾸거나 메서드는 기본 메서드를 숨기지 않습니다 있도록 매개 변수 시그니처를 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]