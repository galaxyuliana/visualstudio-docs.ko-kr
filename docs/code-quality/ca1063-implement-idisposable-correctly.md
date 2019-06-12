---
title: 'CA1063: IDisposable을 올바르게 구현하십시오.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 932805f938e9d96cd944230fcc8aa82a4710da31
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820627"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: IDisposable을 올바르게 구현하십시오.

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

<xref:System.IDisposable?displayProperty=nameWithType> 인터페이스가 올바르게 구현 되지 않았습니다. 이 대 한 가능한 원인:

- <xref:System.IDisposable> 클래스에서 다시 구현 됩니다.

- 완료 reoverridden 됩니다.

- Dispose () 재정의 됩니다.

- Dispose () 메서드를 public이 아닙니다 [봉인](/dotnet/csharp/language-reference/keywords/sealed), 또는 명명 된 **Dispose**합니다.

- Dispose (bool) 보호, 가상 또는 봉인 되지 않은 아닙니다.

- Dispose ()는 봉인 되지 않은 형식에서 Dispose(true)을 호출 해야 합니다.

- 봉인 되지 않은 형식에 대 한 Finalize 구현 중 하나 또는 모두 dispose (bool) 또는 기본 클래스 종료자를 호출 하지 않습니다.

이러한 패턴 중 하나를 위반 CA1063 경고를 트리거합니다.

모든 봉인 되지 않은 형식 선언 및 구현에 <xref:System.IDisposable> 인터페이스를 제공 해야 자체 `protected virtual void Dispose(bool)` 메서드. `Dispose()` 호출 해야 합니다 `Dispose(true)`, 종료자를 호출 해야 하 고 `Dispose(false)`입니다. 선언 하 고 구현 하는 봉인 되지 않은 형식을 만드는 경우 합니다 <xref:System.IDisposable> 정의 해야 인터페이스 `Dispose(bool)` 호출 합니다. 자세한 내용은 [관리 되지 않는 리소스 (.NET 가이드)를 정리](/dotnet/standard/garbage-collection/unmanaged) 하 고 [Dispose 패턴](/dotnet/standard/design-guidelines/dispose-pattern)합니다.

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

모든 <xref:System.IDisposable> 형식을 구현 해야 합니다 [Dispose 패턴](/dotnet/standard/design-guidelines/dispose-pattern) 올바르게 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

코드를 검토 하 고이 위반을 해결 됩니다는 다음 해결 방법 확인:

- 제거 <xref:System.IDisposable> 해당 형식에서 구현 되 고 대신 기본 클래스 Dispose 구현을 재정의 하는 인터페이스 목록에서.

- 사용자의 형식에서 종료자를 제거 하 고 Dispose (bool disposing)를 재정의 '삭제'는 false 코드 경로에 종료 논리를 추가 합니다.

- '삭제' 참 이어야 하는 코드 경로에서 삭제 논리를 배치 및 Dispose (bool disposing)를 재정의 합니다.

- Dispose ()는 public으로 선언 하 고 [봉인](/dotnet/csharp/language-reference/keywords/sealed)합니다.

- Dispose 메서드 이름 바꾸기 **Dispose** public으로 선언 되어 있는지 확인 하 고 [봉인 된](/dotnet/csharp/language-reference/keywords/sealed)합니다.

- dispose (bool) protected로 선언 되어 있는지 확인 하 고, 가상 및 봉인 되지 않은 확인 합니다.

- Dispose(true), 호출 되도록 dispose ()를 수정 호출 <xref:System.GC.SuppressFinalize%2A> 현재 개체 인스턴스에 (`this`, 또는 `Me` Visual Basic의)을 반환 합니다.

- Dispose (false)를 호출 하 고 다음 반환 되도록 종료자를 수정 합니다.

- 선언 하 고 구현 하는 봉인 되지 않은 형식을 만드는 경우는 <xref:System.IDisposable> 인터페이스, 했는지 구현의 <xref:System.IDisposable> 이 단원의 앞에서 설명한 패턴을 따릅니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1063.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="pseudo-code-example"></a>의사 (pseudo) 코드 예제

다음 의사 코드 및 네이티브 리소스를 dispose (bool) 관리를 사용 하는 클래스에서 구현 되는 방법의 일반적인 예제를 제공 합니다.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```

## <a name="see-also"></a>참고자료

- [삭제 패턴 (프레임 워크 디자인 지침)](/dotnet/standard/design-guidelines/dispose-pattern)
- [관리 되지 않는 리소스 (.NET 가이드) 정리](/dotnet/standard/garbage-collection/unmanaged)