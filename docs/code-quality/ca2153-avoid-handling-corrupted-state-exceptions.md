---
title: 'CA2153: 손상된 상태 예외를 처리하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a3e8253936c406a3f84304337b818e0f28f1036f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55950905"
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153: 손상된 상태 예외를 처리하지 마세요.

|||
|-|-|
|TypeName|AvoidHandlingCorruptedStateExceptions|
|CheckId|CA2153|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

[CSE(손상된 상태 예외)](https://msdn.microsoft.com/magazine/dd419661.aspx) 는 프로세스에 메모리 손상이 있음을 나타냅니다. 프로세스 충돌을 허용하는 대신 catch하면 공격자가 손상된 메모리 영역에 익스플로잇을 배치할 수 있는 경우 보안 취약점이 발생할 수 있습니다.

## <a name="rule-description"></a>규칙 설명

CSE는 프로세스의 상태가 손상되었으며 시스템에 의해 catch되지 않았음을 나타냅니다. 손상된 상태 시나리오에서 일반 처리기는 적절한 `HandleProcessCorruptedStateExceptions` 특성으로 메서드를 표시하는 경우에만 예외를 catch합니다. 기본적으로 [CLR(공용 언어 런타임)](/dotnet/standard/clr) 은 CSE에 대한 catch 처리기를 호출하지 않습니다.

로깅 코드조차 공격자가 메모리 손상 버그를 악용할 수 있게 하므로 이러한 종류의 예외를 catch하지 않고 프로세스 충돌을 허용하는 것이 가장 안전한 옵션입니다.

이 경고는 catch(exception) 또는 catch(no exception specification)와 같은 모든 예외를 catch하는 일반 처리기로 CSE를 catch하는 경우에 트리거됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 경고를 해결 하려면 다음 중 하나를 수행 합니다.

- `HandleProcessCorruptedStateExceptions` 특성을 제거합니다. 이렇게 하면 CSE가 catch 처리기로 전달되지 않는 기본 런타임 동작으로 돌아갑니다.

- 특정 예외 유형을 catch하는 처리기 기본 설정에서 일반 catch 처리기를 제거합니다. 이 처리기 코드를 안전 하 게 처리할 수 있습니다 (드물게) 가정 하는 Cse를 포함할 수 있습니다.

- 예외가 호출자에 게 전달 되 고 실행 중인 프로세스를 종료를 보장 하는 catch 처리기에서 CSE를 다시 throw 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="pseudo-code-example"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

다음 의사 코드에서는 이 규칙에 의해 검색되는 패턴을 보여 줍니다.

```csharp
[HandleProcessCorruptedStateExceptions]
// Method to handle and log CSE exceptions.
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle error.
    }
}
```

### <a name="solution-1"></a>솔루션 1

HandleProcessCorruptedExceptions 특성을 제거하면 예외가 처리되지 않습니다.

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle error.
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle error.
    }
}
```

### <a name="solution-2"></a>솔루션 2

일반 catch 처리기를 제거하고 특정 예외 형식만 catch합니다.

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle error.
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle error.
    }
}
```

### <a name="solution-3"></a>솔루션 3

예외를 다시 throw 합니다.

```csharp
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle error.
        throw;
    }
}
```