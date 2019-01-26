---
title: 'CA1064: 예외는 public이어야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d858b5b266b80d84bcbd6eb409a4183105960ee1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018685"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: 예외는 public이어야 합니다.

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 직접 파생 되는 public이 아닌 예외 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="rule-description"></a>규칙 설명
 만 내부 예외가 내부 범위 내에서 표시 됩니다. 예외가 내부 범위 밖에 놓이게 되면 예외를 catch하는 데 기본 예외만 사용할 수 있습니다. 내부 예외에서 상속 되 면 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>, 외부 코드에 예외를 사용 하 여 수행할 작업을 알고에 충분 한 정보가 없습니다.

 이지만, 코드를 나중에 사용 되는 기반으로 내부 예외에 대 한 공용 예외 있으면 코드를 더 자세히 아웃 수 기본 예외를 사용 하 여 지능형 무언가 가정할 수 있습니다. 공용 예외에서 제공 하는 보다 자세한 갖습니다 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 예외를 공용 또는 내부 예외가 아닌 공용 예외에서 파생 <xref:System.Exception>하십시오 <xref:System.SystemException>, 또는 <xref:System.ApplicationException>합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 내부 범위 내에서 개인 예외를 포착 됩니다는 모든 경우에서 확실 한 경우에이 규칙에서 메시지를 표시 하지 않습니다.

## <a name="example"></a>예제
 이 규칙은 첫 번째 예제에서는 메서드, FirstCustomException 예외 클래스 예외에서 직접 파생 되 고 내부 이기 때문입니다. 규칙은 클래스를 public으로 선언 되어 클래스도 예외에서 직접 파생 하지만 SecondCustomException 클래스에서 발생 하지 않습니다. 세 번째 클래스도 발생 하지 않습니다 규칙에서 직접 파생 되지 않습니다 <xref:System.Exception?displayProperty=fullName>하십시오 <xref:System.SystemException?displayProperty=fullName>, 또는 <xref:System.ApplicationException?displayProperty=fullName>합니다.

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
