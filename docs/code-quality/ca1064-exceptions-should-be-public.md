---
title: 'CA1064: 예외는 public이어야 합니다.'
ms.date: 11/04/2016
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
ms.openlocfilehash: b17ccfe66875588ac19c587ff6fcbd889d1e6a44
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922324"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: 예외는 public이어야 합니다.

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
Public이 아닌 예외는, <xref:System.Exception> <xref:System.SystemException>또는 <xref:System.ApplicationException>에서 직접 파생 됩니다.

## <a name="rule-description"></a>규칙 설명
내부 예외는 자체 내부 범위 내부 에서만 볼 수 있습니다. 예외가 내부 범위 밖에 놓이게 되면 예외를 catch하는 데 기본 예외만 사용할 수 있습니다. 내부 예외에서 상속 되 면 <xref:System.Exception>, <xref:System.SystemException>, 또는 <xref:System.ApplicationException>, 외부 코드에 예외를 사용 하 여 수행할 작업을 알고에 충분 한 정보가 없습니다.

그러나 코드에 나중에 내부 예외에 대 한 기준으로 사용 되는 공용 예외가 있는 경우 코드를 더 아웃 하면 기본 예외를 사용 하 여 지능적인 작업을 수행할 수 있다고 가정 하는 것이 합리적입니다. 공용 예외에는, <xref:System.Exception> <xref:System.SystemException>또는 <xref:System.ApplicationException>에서 제공 하는 것 보다 더 많은 정보가 포함 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
예외를 공용으로 설정 하거나, <xref:System.Exception> <xref:System.SystemException>또는 <xref:System.ApplicationException>이 아닌 공용 예외에서 내부 예외를 파생 시킵니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
모든 경우에 전용 예외가 자체 내부 범위 내에서 catch 될 것으로 확신 하는 경우에는이 규칙에서 메시지를 표시 하지 않습니다.

## <a name="example"></a>예제
이 규칙은 예외 클래스가 예외에서 직접 파생 되 고 내부 이기 때문에 첫 번째 예제 메서드인 FirstCustomException에서 발생 합니다. 클래스는 예외에서 직접 파생 되 고 클래스가 public으로 선언 되기 때문에 SecondCustomException 클래스에서 규칙이 발생 하지 않습니다. 또한 세 번째 클래스는, <xref:System.Exception?displayProperty=fullName> <xref:System.SystemException?displayProperty=fullName>또는 <xref:System.ApplicationException?displayProperty=fullName>에서 직접 파생 되지 않으므로 규칙을 실행 하지 않습니다.

[!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
