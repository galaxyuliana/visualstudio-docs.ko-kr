---
title: 'CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c75c7c240f694b18caacefc0f9b1ee07f54faf36
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920796"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
.NET Framework 버전 1.0 및 1.1에서는 공용 또는 보호 된 `try` 메서드에 `finally` 블록이 포함 되어 있습니다 /. `catch` / 블록이 보안 상태를 다시 설정 하는 것으로 표시 되 고 `finally` 블록에 포함 되지 않습니다. `finally`

## <a name="rule-description"></a>규칙 설명
이 규칙은 `try` 호출 스택에 있는 악성 예외 필터에 취약할 수 있는 .NET Framework 버전 1.0 및 1.1를 대상으로 하는 코드의 블록을 찾습니다 / `finally` . Try 블록에서 가장과 같은 중요 한 작업이 발생 하 고 예외가 throw 되는 경우 필터는 `finally` 블록 이전에 실행할 수 있습니다. 가장 예제에서는 필터가 가장 된 사용자로 실행 됨을 의미 합니다. 필터는 현재 Visual Basic 에서만 구현 됩니다.

> [!NOTE]
> .NET Framework 버전 2.0 이상에서는 다시 설정이 메서드 내에서 직접 다시 설정 된 `try` 경우 런타임이 악성 예외 필터에서 `finally` 블록을 자동으로 보호 / `catch` /  합니다. 예외 블록을 포함 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
래핑 `try` 되지않은를`finally` 외부 try 블록에 넣습니다. / 다음 두 번째 예제를 참조 하세요. 이렇게 하면가 `finally` 필터 코드 보다 먼저 실행 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="pseudo-code-example"></a>의사 코드 예제

### <a name="description"></a>Description

다음 의사 코드에서는 이 규칙에 의해 검색되는 패턴을 보여 줍니다.

```csharp
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

다음 의사 코드는 코드를 보호 하 고이 규칙을 충족 하는 데 사용할 수 있는 패턴을 보여 줍니다.

```csharp
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```