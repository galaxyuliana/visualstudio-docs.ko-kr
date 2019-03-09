---
title: 'CA2007: 직접 작업을 기다리지 않습니다'
ms.date: 03/08/2019
ms.topic: reference
f1_keywords:
- CA2007
- DoNotDirectlyAwaitATaskAnalyzer
helpviewer_keywords:
- CA2007
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.openlocfilehash: 8e94b67d1924e2144f658cd6bcd5989751efdb85
ms.sourcegitcommit: 1024f336dcd8e8a4c50b9a9ad8ec85b6e70073a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57699682"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007: 직접 작업을 기다리지 않습니다

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

비동기 메서드이기 [기다리는](/dotnet/csharp/language-reference/keywords/await) 는 <xref:System.Threading.Tasks.Task> 직접.

## <a name="rule-description"></a>규칙 설명

비동기 메서드를 대기 하는 경우는 <xref:System.Threading.Tasks.Task> 연속 작업을 만든 동일한 스레드에서 발생 하는 직접. 이 동작은 성능 측면에서 비용이 많이 들 수 있으며 UI 스레드에서 교착 상태가 발생할 수 있습니다. 호출 해 보십시오 <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> 연속에 대 한 의도 알립니다.

이 규칙에서 도입 되었습니다 [FxCop 분석기](install-fxcop-analyzers.md) "레거시" (정적 코드 분석)에 없는 및 FxCop 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

위반 문제를 해결 하려면 호출 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> 에서 대기 된 <xref:System.Threading.Tasks.Task>합니다. 전달할 수 있습니다 `true` 나 `false` 에 대 한는 `continueOnCapturedContext` 매개 변수입니다.

- 호출 `ConfigureAwait(true)` 작업은 명시적으로 호출 하지와 동일한 동작이 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A>합니다. 이 메서드를 명시적으로 호출 하 여 알아낼 수 있습니다 판독기 의도적으로 원래 동기화 컨텍스트에서 연속 작업을 수행 하려고 합니다.

- 호출 `ConfigureAwait(false)` 스레드 풀에 대 한 연속 작업을 예약 하려면 작업을 피할 UI 스레드에서 교착 상태가 발생 합니다. 전달 `false` 앱 독립적인 라이브러리에 대 한 적합 한 옵션입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

소비자는 그래픽 사용자 인터페이스 (GUI) 앱 인지 또는 소비자에 없는 경우 사용자가 알고 있는 경우이 경고를 표시 하지 않을 수는 <xref:System.Threading.SynchronizationContext>합니다.

## <a name="example"></a>예제

다음 코드 조각에서는 경고를 생성합니다.

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

위반을 해결 하려면 호출 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A> 에서 대기 된 <xref:System.Threading.Tasks.Task>:

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="see-also"></a>참고자료

- [Configureawait (false) 사용 하 여 작업을 대기 해야 하나요?](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [Visual Studio에서 FxCop 분석기 설치](install-fxcop-analyzers.md)