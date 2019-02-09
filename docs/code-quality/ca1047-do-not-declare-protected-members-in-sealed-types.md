---
title: 'CA1047: protected 멤버를 sealed 형식으로 선언하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c138c05d755b05275755f96776764604997cbbcd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55921551"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: protected 멤버를 sealed 형식으로 선언하지 마세요.

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 공용 형식이 `sealed` (`NotInheritable` Visual basic에서) 하 고 보호 된 멤버 또는 중첩된 된 보호 형식을 선언 합니다. 이 규칙에 대 한 위반을 보고 하지 않습니다 <xref:System.Object.Finalize%2A> 메서드가이 패턴을 따라야 합니다.

## <a name="rule-description"></a>규칙 설명
 형식에서는 상속하는 형식에서 멤버에 액세스하거나 멤버를 재정의할 수 있도록 하기 위해 protected 멤버를 선언합니다. 정의상, 봉인 된 형식에 메서드를 보호 하는 의미를 호출할 수 없습니다. 봉인 된 형식에서 상속할 수 없습니다.

 C# 컴파일러에서이 오류에 대 한 경고가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 멤버의 액세스 수준을 개인으로 변경 하거나 형식을 상속 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 형식이 현재 상태의 유지 관리 문제가 발생할 수 있습니다를 모든 혜택을 제공 하지 않습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]