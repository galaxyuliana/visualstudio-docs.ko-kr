---
title: 'CA1031: 일반적인 예외 형식을 catch하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e9746119c746679817076c86e3d5a9080cec30d9
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744693"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: 일반적인 예외 형식을 catch하지 마세요.

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 와 같은 일반 예외 <xref:System.Exception?displayProperty=fullName> 또는 <xref:System.SystemException?displayProperty=fullName> 에서 발견 되는 `catch` 문이나와 같은 일반 catch 절 `catch()` 사용 됩니다.

## <a name="rule-description"></a>규칙 설명
 일반 예외는 catch하면 안 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 보다 구체적인 예외를 catch 하거나의 마지막 문으로 일반 예외를 다시 throw 된 `catch` 블록입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 일반적인 예외 형식을 catch 할 라이브러리 사용자 로부터 런타임 문제를 숨길 수 있습니다 및 디버깅을 더 어렵게 만들 수 있습니다.

> [!NOTE]
> .NET Framework 4부터 공용 언어 런타임 (CLR) 더 이상 제공 운영 체제 및의 액세스 위반과 같이 관리 코드에서 발생 하는 손상 된 상태 예외 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)], 관리 코드에서 처리 해야 합니다. .NET Framework 4에서에서 응용 프로그램 컴파일 또는 이상 버전을 하 고 손상 된 상태 예외 처리를 유지 관리 하는 경우 적용할 수 있습니다는 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 손상 된 상태 예외를 처리 하는 메서드 특성입니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 형식 및 올바르게 구현 하는 형식을 `catch` 블록입니다.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2200: 스택 정보를 유지 하도록 다시 throw](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)