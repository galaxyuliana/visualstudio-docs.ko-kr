---
title: '방법: 비동기 Visual Studio 서비스 제공 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9628a3e352d2662fe150ec7ef4cda7c79a2fdffa
ms.sourcegitcommit: 01c3c9dcade5d913bde2c7efa8c931a7b04e6cd0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67365687"
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>방법: 비동기 Visual Studio 서비스를 제공 합니다.
UI 스레드를 차단 하지 않고 서비스를 가져오려는 경우 비동기 서비스를 만들고 백그라운드 스레드에서 패키지를 로드 해야 합니다. 이 목적을 위해 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage> 아닌 <xref:Microsoft.VisualStudio.Shell.Package>, 비동기 패키지의 특수 비동기 메서드를 사용 하 여 서비스를 추가 합니다.

 동기 Visual Studio 서비스를 제공 하는 방법에 대 한 내용은 [방법: 서비스 제공](../extensibility/how-to-provide-a-service.md)합니다.

## <a name="implement-an-asynchronous-service"></a>비동기 서비스 구현

1. VSIX 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트** > **Visual C#**  >  **확장성** > **VSIX 프로젝트**). 프로젝트 이름을 **TestAsync**합니다.

2. VSPackage 프로젝트에 추가 합니다. 프로젝트 노드를 선택 합니다 **솔루션 탐색기** 누릅니다 **추가** > **새 항목** > **Visual C# 항목**  >  **확장성** > **Visual Studio 패키지**합니다. 이 파일의 이름을 *TestAsyncPackage.cs*합니다.

3. *TestAsyncPackage.cs*, 패키지에서 상속 하도록 변경할 `AsyncPackage` 대신 `Package`:

    ```csharp
    public sealed class TestAsyncPackage : AsyncPackage
    ```

4. 서비스를 구현 하려면 세 가지 형식을 만들 필요 합니다.

    - 서비스를 식별 하는 인터페이스입니다. 이러한 인터페이스의 대부분은 빈, 즉, 해당 메서드가 없는 갖습니다 쿼리 서비스에만 사용 됩니다.

    - 서비스 인터페이스를 설명 하는 인터페이스입니다. 이 인터페이스 메서드를 구현할 수를 포함 합니다.

    - 서비스와 서비스 인터페이스를 구현 하는 클래스입니다.

5. 다음 예제에서는 세 가지 형식의 매우 기본적인 구현을 보여 줍니다. 서비스 클래스의 생성자는 서비스 공급자를 설정 해야 합니다. 이 예제 패키지 코드 파일에 서비스를 추가 합니다.

6. 다음 추가 패키지 파일에 문을 사용 하 여:

    ```csharp
    using System.Threading;
    using System.Threading.Tasks;
    using System.Runtime.CompilerServices;
    using System.IO;
    using Microsoft.VisualStudio.Threading;
    using IAsyncServiceProvider = Microsoft.VisualStudio.Shell.IAsyncServiceProvider;
    using Task = System.Threading.Tasks.Task;
    ```

7. 비동기 서비스 구현은 다음과 같습니다. 참고 생성자에서 동기 서비스 공급자 보다는 비동기 서비스 공급자를 설정 해야 합니다.

    ```csharp
    public class TextWriterService : STextWriterService, ITextWriterService
    {
        private IAsyncServiceProvider asyncServiceProvider;

        public TextWriterService(IAsyncServiceProvider provider)
        {
            // constructor should only be used for simple initialization
            // any usage of Visual Studio service, expensive background operations should happen in the
            // asynchronous InitializeAsync method for best performance
            asyncServiceProvider = provider;
        }

        public async Task InitializeAsync(CancellationToken cancellationToken)
        {
            await TaskScheduler.Default;
            // do background operations that involve IO or other async methods

            await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);
            // query Visual Studio services on main thread unless they are documented as free threaded explicitly.
            // The reason for this is the final cast to service interface (such as IVsShell) may involve COM operations to add/release references.

            IVsShell vsShell = this.asyncServiceProvider.GetServiceAsync(typeof(SVsShell)) as IVsShell;
            // use Visual Studio services to continue initialization
        }

        public async Task WriteLineAsync(string path, string line)
        {
            StreamWriter writer = new StreamWriter(path);
            await writer.WriteLineAsync(line);
            writer.Close();
        }
    }

    public interface STextWriterService
    {
    }

    public interface ITextWriterService
    {
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);
    }
    ```

## <a name="register-a-service"></a>서비스 등록
 서비스를 등록 하려면 추가 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 서비스를 제공 하는 패키지에 있습니다. 패키지와 서비스 모두 비동기 로드를 지원 하는지 확인 해야 다른 동기 서비스를 등록 합니다.

- 추가 해야 합니다는 **AllowsBackgroundLoading = true** 필드를 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 참조는 PackageRegistrationAttribute 대 한 자세한 내용은 패키지를 비동기적으로 초기화 되도록 [등록 및 Vspackage 등록 취소](../extensibility/registering-and-unregistering-vspackages.md)합니다.

- 추가 해야 합니다 **IsAsyncQueryable = true** 필드를 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 서비스 인스턴스를 비동기적으로 초기화할 수 있도록 합니다.

  예로 `AsyncPackage` 비동기 서비스 등록을 사용 하 여:

```csharp
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]
[Guid(TestAsyncPackage.PackageGuidString)]
public sealed class TestAsyncPackage : AsyncPackage
{. . . }
```

## <a name="add-a-service"></a>서비스 추가

1. *TestAsyncPackage.cs*를 제거 합니다 `Initialize()` 메서드와 재정의 `InitializeAsync()` 메서드. 서비스를 추가 하 고 서비스를 만드는 콜백 메서드를 추가 합니다. 서비스 추가 비동기 이니셜라이저의 예는 다음과 같습니다.

    ```csharp
    protected override async Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)
    {
        await base.InitializeAsync(cancellationToken, progress);
        this.AddService(typeof(STextWriterService), CreateTextWriterService);
    }

    ```

2. 에 대 한 참조를 추가 *Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll*합니다.

3. 콜백 메서드를 만들고 서비스를 반환 하는 비동기 메서드로 구현 합니다.

    ```csharp
    public async Task<object> CreateTextWriterService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)
    {
        TextWriterService service = new TextWriterService(this);
        await service.InitializeAsync(cancellationToken);
        return service;
    }

    ```

## <a name="use-a-service"></a>서비스를 사용 합니다.
 이제 서비스를 가져올 수 있으며 해당 메서드를 사용할 수 있습니다.

1. 이니셜라이저를에서이 보여 주지만 서비스를 사용 하려는 서비스 든 가져올 수 있습니다.

    ```csharp
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)
    {
        await base.InitializeAsync(cancellationToken, progress);
        this.AddService(typeof(STextWriterService), CreateTextWriterService);

        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;
        string userpath = @"C:\MyDir\MyFile.txt";
        await textService.WriteLineAsync(userpath, "this is a test");
    }

    ```

     반드시 변경 `userpath` 파일 이름 및 컴퓨터에 적합 한 경로.

2. 빌드 및 코드를 실행 합니다. Visual Studio의 실험적 인스턴스가 표시 되 면 솔루션을 엽니다. 이 인해는 `AsyncPackage` autoload를 합니다. 이니셜라이저를 실행 하는 경우 지정한 위치에서 파일을 찾아야 합니다.

## <a name="use-an-asynchronous-service-in-a-command-handler"></a>명령 처리기에서 비동기 서비스 사용
 비동기 서비스 메뉴 명령을 사용 하는 방법의 예는 다음과 같습니다. 다른 아닌 비동기 메서드에서 서비스를 사용 하려면 여기에 표시 된 절차를 사용할 수 있습니다.

1. 프로젝트에 메뉴 명령을 추가 합니다. (에 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 선택 **추가** > **새 항목**  >   **확장성** > **사용자 지정 명령**.) 명령 파일 이름을 *TestAsyncCommand.cs*합니다.

2. 사용자 지정 명령 템플릿을 다시 추가 합니다 `Initialize()` 메서드를를 *TestAsyncPackage.cs* 명령을 초기화 하기 위해 파일. 에 `Initialize()` 메서드 명령을 초기화 하는 줄을 복사 합니다. 다음과 같이 표시됩니다.

    ```csharp
    TestAsyncCommand.Initialize(this);
    ```

     이 줄을 이동 합니다 `InitializeAsync()` 의 메서드를 *AsyncPackageForService.cs* 파일입니다. 레지스트리를 사용 하 여 명령을 초기화 하기 전에 주 스레드를 전환 해야 합니다 이므로이 비동기 초기화에 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>입니다. 이제 다음과 같이 표시 됩니다.

    ```csharp

    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)
    {
        await base.InitializeAsync(cancellationToken, progress);
        this.AddService(typeof(STextWriterService), CreateTextWriterService);

        ITextWriterService textService =
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;
        
        string userpath = @"C:\MyDir\MyFile.txt";
        await textService.WriteLineAsync(userpath, "this is a test");

        await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);
        TestAsyncCommand.Initialize(this);
    }

    ```

3. 삭제 된 `Initialize()` 메서드.

4. 에 *TestAsyncCommand.cs* 파일에서 찾기는 `MenuItemCallback()` 메서드. 메서드의 본문을 삭제 합니다.

5. using 문을 추가합니다.

    ```csharp
    using System.IO;
    ```

6. 라는 비동기 메서드를 추가 `UseTextWriterAsync()`, 서비스를 가져와 해당 메서드를 사용 하는:

    ```csharp
    private async System.Threading.Tasks.Task UseTextWriterAsync()
    {
        // Query text writer service asynchronously to avoid a blocking call.
        ITextWriterService textService =
           await AsyncServiceProvider.GlobalProvider.GetServiceAsync(typeof(STextWriterService))
              as ITextWriterService;

        string userpath = @"C:\MyDir\MyFile.txt";
        await textService.WriteLineAsync(userpath, "this is a test");
       }

    ```

7. 이 메서드를 호출 합니다 `MenuItemCallback()` 메서드:

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        UseTextWriterAsync();
    }

    ```

8. 솔루션을 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 되 면 이동 합니다 **도구** 메뉴를 **TestAsyncCommand 호출** 메뉴 항목입니다. 여기를 클릭 하는 경우는 TextWriterService 지정한 파일에 씁니다. (필요가 없습니다 솔루션을 열고 로드할 패키지를 해도 명령을 호출 하기 때문에.)

## <a name="see-also"></a>참고자료
- [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)
