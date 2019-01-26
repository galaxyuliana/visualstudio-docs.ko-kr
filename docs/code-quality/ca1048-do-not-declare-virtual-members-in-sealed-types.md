---
title: 'CA1048: 가상 멤버를 sealed 형식으로 선언하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 531590eee7804debfc8ccfb9a8e508107fba71df
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006730"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: 가상 멤버를 sealed 형식으로 선언하지 마세요.

|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 형식이 봉인 되어 있으며 둘 다는 메서드를 선언 `virtual` (`Overridable` Visual Basic에서) 및 최종 없습니다. 이 규칙에서이 패턴을 따라야 하는 대리자 형식에 대 한 위반을 보고 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 상속 형식이 가상 메서드의 구현을 재정의할 수 있도록 하기 위해 형식은 메서드를 가상으로 선언합니다. 정의상, 가상 메서드를 sealed 형식에 대 의미가 있도록 봉인 된 형식에서 상속할 수 없습니다.

 Visual Basic 및 C# 컴파일러는이 규칙을 위반 하는 형식을 허용 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 가상이 아닌 메서드를 확인 하거나 형식을 상속 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 형식이 현재 상태의 유지 관리 문제가 발생할 수 있습니다를 모든 혜택을 제공 하지 않습니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]