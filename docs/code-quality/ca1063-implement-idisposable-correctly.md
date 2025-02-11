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
ms.openlocfilehash: 837659ca24eb66995626668185500db7bc32bbd7
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547378"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: IDisposable을 올바르게 구현하십시오.

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

<xref:System.IDisposable?displayProperty=nameWithType> 인터페이스가 제대로 구현 되지 않았습니다. 가능한 원인은 다음과 같습니다.

- <xref:System.IDisposable>는 클래스에서 다시 구현입니다.

- `Finalize`다시 정의 됩니다.

- `Dispose()`이 재정의 됩니다.

- 메서드가 public이 아니거나 [sealed](/dotnet/csharp/language-reference/keywords/sealed)이거나 이름이 Dispose 인 경우 `Dispose()`

- `Dispose(bool)`는 보호 되지 않거나, 가상 이거나, 봉인 되지 않습니다.

- 봉인 되지 않은 형식의 `Dispose()` 경우는 `Dispose(true)`를 호출 해야 합니다.

- 봉인 되지 않은 형식의 `Finalize` 경우 구현은 또는 둘 다 `Dispose(bool)` 또는 기본 클래스 종료자를 호출 하지 않습니다.

이러한 패턴 중 하나를 위반 하면 경고 CA1063 트리거됩니다.

인터페이스를 <xref:System.IDisposable> 선언 하 고 구현 하는 봉인 되지 않은 모든 형식은 `protected virtual void Dispose(bool)` 자체 메서드를 제공 해야 합니다. `Dispose()`는를 `Dispose(true)`호출 해야 하 고 종료자는 `Dispose(false)`를 호출 해야 합니다. <xref:System.IDisposable> 인터페이스를 선언 하 고 구현 하는 봉인 되지 않은 형식을 만드는 경우이를 `Dispose(bool)` 정의 하 고 호출 해야 합니다. 자세한 내용은 [관리 되지 않는 리소스 정리 (.net 가이드)](/dotnet/standard/garbage-collection/unmanaged) 및 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)을 참조 하세요.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

모든 <xref:System.IDisposable> 형식은 [Dispose 패턴](/dotnet/standard/design-guidelines/dispose-pattern) 을 올바르게 구현 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

코드를 검사 하 고 다음 해결 방법을 확인 하 여이 위반을 해결 합니다.

- 형식 <xref:System.IDisposable> 에 의해 구현 된 인터페이스 목록에서을 제거 하 고 대신 기본 클래스 Dispose 구현을 재정의 합니다.

- 형식에서 종료자를 제거 하 고 Dispose (bool disposing)를 재정의 한 후 ' disposing '이 false 인 코드 경로에 종료 논리를 넣습니다.

- Dispose (bool disposing)를 재정의 하 고 ' disposing '이 true 인 코드 경로에 삭제 논리를 넣습니다.

- Dispose ()가 public 및 [sealed](/dotnet/csharp/language-reference/keywords/sealed)로 선언 되었는지 확인 합니다.

- Dispose 메서드의 이름을 **dispose** 로 바꾸고 public 및 [sealed](/dotnet/csharp/language-reference/keywords/sealed)로 선언 되어 있는지 확인 합니다.

- Dispose (bool)가 protected, virtual 및 봉인 되지 않음으로 선언 되었는지 확인 합니다.

- Dispose ()를 수정 하 여 dispose (true)를 호출한 다음 현재 <xref:System.GC.SuppressFinalize%2A> 개체 인스턴스 (`this`또는 `Me` Visual Basic)에서를 호출한 다음을 반환 합니다.

- Dispose (false)를 호출 하 고를 반환 하도록 종료자를 수정 합니다.

- 인터페이스를 <xref:System.IDisposable> 선언 하 고 구현 하는 봉인 되지 않은 형식을 만드는 경우의 <xref:System.IDisposable> 구현이이 단원의 앞 부분에서 설명한 패턴을 따르는지 확인 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1063.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="pseudo-code-example"></a>의사 코드 예제

다음 의사 코드는 관리 되는 리소스와 네이티브 리소스를 사용 하는 클래스에서 Dispose (bool)를 구현 하는 방법에 대 한 일반적인 예를 제공 합니다.

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

- [Dispose 패턴 (프레임 워크 디자인 지침)](/dotnet/standard/design-guidelines/dispose-pattern)
- [관리 되지 않는 리소스 정리 (.NET 가이드)](/dotnet/standard/garbage-collection/unmanaged)