---
title: 언어 서버 프로토콜 확장 추가 | Microsoft Docs
ms.date: 11/14/2017
ms.topic: conceptual
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d7590350fdcfb74f90cd4441e97503a60b298c66
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954282"
---
# <a name="add-a-language-server-protocol-extension"></a>언어 서버 프로토콜 확장 추가

언어 서버 프로토콜 (LSP)는 언어 서비스 기능을 다양 한 코드 편집기를 제공 하는 데 사용 되는 JSON RPC v2.0의 형태로 일반적인 프로토콜입니다. 프로토콜을 사용 하 여 개발자 언어 오류를 진단, IntelliSense와 같은 서비스 기능을 제공 하면 귀하의 LSP를 지 원하는 다양 한 코드 편집기에 모든 등 참조 찾기에 단일 언어 서버를 작성할 수 있습니다. 일반적으로 Visual Studio에서 언어 서비스를 추가할 수 있습니다 TextMate 문법 파일을 사용 하 여 Visual Studio 확장성 Api의 전체 집합을 사용 하 여 사용자 지정 언어 서비스를 작성 또는 구문 강조 표시와 같은 기본 기능을 제공 하에 다양 한 데이터를 제공 합니다. 이제 지원 하면 귀하의 LSP는 세 번째 옵션을 제공 합니다.

![Visual Studio에서 언어 서버 프로토콜 서비스](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>언어 서버 프로토콜

![언어 서버 프로토콜 구현](media/lsp-implementation.png)

이 문서에는 언어 LSP 기반 서버를 사용 하는 Visual Studio 확장 프로그램을 만드는 방법을 설명 합니다. 언어 LSP 기반 서버를 미리 만들어 둔 Visual Studio에 통합 하려는 가정 합니다.

Visual Studio 내에서 지원에 대 한 언어 서버와 통신할 수 있는 스트림 기반 전송 메커니즘을 통해 클라이언트 (Visual Studio) 예를 들어:

* 표준 입력/출력 스트림
* 명명 된 파이프
* 소켓 (TCP 전용)

LSP 및 Visual Studio에서 지원을의 목적은 Visual Studio 제품의 일부분이 아닌 온 보 딩 언어 서비스 하는 것입니다. Visual Studio에서 기존 언어 서비스 (예: C#)를 확장 하는 것이 아닙니다. 기존 언어를 확장 하려면 언어 서비스의 확장성 가이드를 참조 하세요 (예를 들어 합니다 [.NET 컴파일러 플랫폼 "Roslyn"](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md)).

프로토콜 자체에 대 한 자세한 내용은 설명서를 참조 [여기](https://github.com/Microsoft/language-server-protocol)합니다.

샘플 언어 server 또는 Visual Studio Code에 기존 언어 서버를 통합 하는 방법 참조 설명서를 만드는 방법에 대 한 자세한 내용은 [여기](https://code.visualstudio.com/docs/extensions/example-language-server)합니다.

## <a name="language-server-protocol-features-supported"></a>지원 되는 언어 서버 프로토콜 기능

지금 Visual Studio에서 다음과 같은 LSP 기능이 지원 됩니다.

메시지 | Visual Studio에서 지지도
--- | ---
초기화 | 예
초기화됨 | 예
종료 | 예
종료 | 예
$/cancelRequest | 예
window/showMessage | 예
window/showMessageRequest | 예
window/logMessage | 예
원격 분석/이벤트 |
client/registerCapability |
client/unregisterCapability |
workspace/didChangeConfiguration | 예
workspace/didChangeWatchedFiles | 예
작업 영역/기호 | 예
workspace/executeCommand | 예
workspace/applyEdit | 예
textDocument/publishDiagnostics | 예
textDocument/didOpen | 예
textDocument/didChange | 예
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | 예
textDocument/didClose | 예
textDocument/완료 | 예
completion/resolve | 예
textDocument/가리키기 | 예
textDocument/signatureHelp | 예
textDocument/참조 | 예
textDocument/documentHighlight | 예
textDocument/documentSymbol | 예
textDocument/서식 지정 | 예
textDocument/rangeFormatting | 예
textDocument/onTypeFormatting |
textDocument/정의 | 예
textDocument/codeAction | 예
textDocument/codeLens |
codeLens/resolve |
textDocument/documentLink |
documentLink/resolve |
textDocument/rename | 예

## <a name="getting-started"></a>시작

> [!NOTE]
> Visual Studio 15.8 미리 보기 3, 공용 언어 서버 프로토콜에 대 한 지원부터 Visual Studio에 빌드됩니다. 미리 보기를 사용 하 여 LSP 확장 구축 하는 경우 [언어 서버 클라이언트 VSIX](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview) 버전인을 15.8 미리 보기 3 이상으로 업그레이드 한 후 작업을 하지 않을 것입니다. 작업을 다시 LSP 확장을 가져오려면 다음을 수행 해야 합니다.
>
> 1. Microsoft Visual Studio 언어 서버 프로토콜 Preview VSIX를 제거 합니다. 15.8 Preview 4부터 Visual Studio에서 업그레이드를 수행 될 때마다 자동으로 감지 하 고 업그레이드 프로세스를 VSIX preview를 제거 합니다.
>
> 2. 에 대 한 미리 보기가 아닌 최신 Nuget 참조를 업데이트할 [LSP 패키지](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)합니다.
>
> 3. VSIX 매니페스트에 종속성을 Microsoft Visual Studio 언어 서버 프로토콜 미리 보기 VSIX를 제거 합니다.
>
> 4. VSIX 설치 대상에 대 한 하한값으로 Visual Studio 15.8 미리 보기 3을 지정 해야 합니다.
>
> 5. 다시 빌드하고 다시 배포 합니다.

### <a name="create-a-vsix-project"></a>VSIX 프로젝트를 만듭니다

언어 LSP 기반 서버를 사용 하는 언어 서비스 확장을 만들려면 먼저 했는지 확인 합니다 **Visual Studio 확장 개발** 워크 로드가 VS 인스턴스에 대 한 설치 합니다.

다음으로 이동 하 여 새 빈 VSIXProject를 만듭니다 **파일** > **새 프로젝트** > **Visual C#**  >   **확장성** > **VSIX 프로젝트**:

![vsix 프로젝트 만들기](media/lsp-vsix-project.png)

### <a name="language-server-and-runtime-installation"></a>언어 서버 및 런타임 설치

기본적으로 서버를 지 원하는 언어 LSP 기반 Visual Studio에서 만든 확장 언어 서버 자체 또는 실행 하는 데 필요한 런타임 포함 되지 않습니다. 확장 개발자는 language 서버와 필요한 런타임을 배포 하는 일을 담당 합니다. 이렇게 하는 방법은 여러 가지가 있습니다.

* 언어 서버 콘텐츠 파일로 VSIX에 포함할 수 있습니다.
* 언어 서버를 설치 하려면 MSI 만들기 및/또는 런타임 필요 합니다.
* 서버 런타임 및 언어를 구하는 방법 Marketplace 한다는 사용자에 게 지침을 제공 합니다.

### <a name="textmate-grammar-files"></a>TextMate 문법 파일

LSP는 언어에 대 한 텍스트 색 지정을 제공 하는 방법에 대 한 사양을 포함 되지 않습니다. 확장 개발자는 Visual Studio에서 언어에 대 한 사용자 지정 색 지정을 제공 하려면 TextMate 문법 파일을 사용할 수 있습니다. 사용자 지정 TextMate 문법 이나 테마 파일을 추가 하려면 다음이 단계를 수행 합니다.

1. 확장 내에서 "문법" 라는 폴더를 만듭니다 (또는 원하는 수)입니다.

2. 내 합니다 *문법* 폴더를 포함  *\*.tmlanguage*를  *\*.plist*를  *\*.tmtheme*, 또는  *\*.json* 파일을 사용자 지정 색 지정을 제공 합니다.

3. 선택한 파일을 마우스 오른쪽 단추로 클릭 **속성**합니다. 변경 합니다 **빌드** 작업을 **콘텐츠** 하며 **VSIX에 포함** 속성을 true로 합니다.

4. 만들기는 *.pkgdef* 파일과 비슷한이 줄을 추가 합니다.

    ```
    [$RootKey$\TextMate\Repositories]
    "MyLang"="$PackageFolder$\Grammars"
    ```

5. 선택한 파일을 마우스 오른쪽 단추로 클릭 **속성**합니다. 변경 합니다 **빌드** 작업을 **콘텐츠** 하며 **VSIX에 포함** 속성을 true로 합니다.

이전 단계를 완료 한 후를 *문법* 폴더가 패키지의 설치에 추가 됩니다 리포지토리 원본 디렉터리 라는 'MyLang' ('MyLang' 명확성을 위해 이름만 이며 고유한 문자열일 수 있습니다). 모든 문법 (*.tmlanguage* 파일) 및 테마 파일 (*.tmtheme* 파일)이 디렉터리는 미래를 선택 하 고 TextMate와 함께 제공 되는 기본 제공 문법 대체 합니다. 열려 있는 파일의 확장명과 일치 하는 문법 파일의 선언 된 확장, TextMate 개입 됩니다.

## <a name="create-a-simple-language-client"></a>간단한 언어 클라이언트 만들기

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>기본 인터페이스- [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

VSIX 프로젝트를 만든 후 다음 NuGet 패키지를 프로젝트에 추가 합니다.

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> 이전 단계를 완료 한 후 NuGet 패키지에는 종속성을 가져오고, Newtonsoft.Json 및 StreamJsonRpc 패키지도 프로젝트에 추가 됩니다. **Visual Studio의 버전에 해당 새 버전을 설치할 것이 확실 하지 않은 경우 이러한 패키지를 업데이트 하지 않으면 하는 확장 대상**합니다. 어셈블리는 포함 되지 않습니다-VSIX에 대신 이러한 픽업 됩니다 Visual Studio 설치 디렉터리에서. 확장 프로그램 사용자의 컴퓨터에 설치 된 것 보다 최신 버전의 어셈블리를 참조 하는 경우 *작동 하지 것입니다*합니다.

구현 하는 새 클래스를 만들 수 있습니다 합니다 [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017) 인터페이스, 언어 LSP 기반 서버에 연결 하는 언어 클라이언트에 필요한 기본 인터페이스입니다.

다음은 샘플입니다.

```csharp
namespace MockLanguageExtension
{
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
        public string Name => "Bar Language Extension";

        public IEnumerable<string> ConfigurationSections => null;

        public object InitializationOptions => null;

        public IEnumerable<string> FilesToWatch => null;

        public event AsyncEventHandler<EventArgs> StartAsync;
        public event AsyncEventHandler<EventArgs> StopAsync;

        public async Task<Connection> ActivateAsync(CancellationToken token)
        {
            await Task.Yield();

            ProcessStartInfo info = new ProcessStartInfo();
            info.FileName = Path.Combine(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location), "Server", @"MockLanguageServer.exe");
            info.Arguments = "bar";
            info.RedirectStandardInput = true;
            info.RedirectStandardOutput = true;
            info.UseShellExecute = false;
            info.CreateNoWindow = true;

            Process process = new Process();
            process.StartInfo = info;

            if (process.Start())
            {
                return new Connection(process.StandardOutput.BaseStream, process.StandardInput.BaseStream);
            }

            return null;
        }

        public async Task OnLoadedAsync()
        {
            await StartAsync.InvokeAsync(this, EventArgs.Empty);
        }

        public Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

구현 해야 하는 기본 메서드는 [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) 하 고 [ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017)합니다. [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) Visual Studio 확장 로드 및 언어 서버를 시작할 준비가 때 호출 됩니다. 이 메서드를 호출할 수 있습니다 합니다 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 대리자 언어 서버 시작 되어야 하거나 추가 논리를 수행 하 고 호출 신호를 즉시 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 나중입니다. **언어 서버를 활성화 하려면 StartAsync 시점에서 호출 해야 합니다.**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017) 메서드를 호출 하 여 최종적으로 호출 되는 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 대리자를 언어 서버를 시작 하 고 연결을 설정 하는 논리가 포함 합니다. 서버에 쓰고 서버에서 읽기 위한 스트림을 포함 하는 연결 개체를 반환 합니다. 여기에 throw 된 예외 포착 되 고 Visual Studio에서 InfoBar 메시지를 통해 사용자에 게 표시 됩니다.

### <a name="activation"></a>활성화

언어 클라이언트 클래스를 구현한 방법이 될 Visual Studio로 로드 하 고 활성화를 정의 하려면 두 가지 특성을 정의 하는 것이 해야 합니다.

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio에서는 [MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (Managed Extensibility Framework)는 확장성 지점을 관리 합니다. 합니다 [내보내기](/dotnet/api/system.componentmodel.composition.exportattribute) 이 클래스 확장 지점으로 선택 하 고 적절 한 시간 로드는 Visual Studio에 특성을 나타냅니다.

MEF를 사용 하려면 또한 VSIX 매니페스트의 자산으로 MEF를 정의 해야 합니다.

VSIX 매니페스트 디자이너를 열고로 이동 합니다 **자산** 탭:

![MEF 자산 추가](media/lsp-add-asset.png)

새 자산을 만들려면 새로 만들기를 클릭 합니다.

![MEF 자산을 정의 합니다.](media/lsp-define-asset.png)

* **Type**: Microsoft.VisualStudio.MefComponent
* **원본**: 현재 솔루션의 프로젝트
* **프로젝트**: [프로젝트]

### <a name="content-type-definition"></a>콘텐츠 형식 정의

현재 LSP 기반 언어 서버 확장 프로그램을 로드 하는 유일한 방법은 파일 콘텐츠 형식에 따라 됩니다. 즉, 언어 클라이언트 클래스를 정의 하는 경우 (구현 [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)), 형식을 정의 해야 합니다를 열 때 사용자 지정 확장을 로드 하면 파일입니다. 에 정의 된 콘텐츠 형식과 일치 하는 파일이 열린 경우 다음 확장 로드 되지 않습니다.

하나 이상의 ContentTypeDefinition 클래스 정의 통해 이루어집니다.

```csharp
namespace MockLanguageExtension
{
    public class BarContentDefinition
    {
        [Export]
        [Name("bar")]
        [BaseDefinition(CodeRemoteContentDefinition.CodeRemoteContentTypeName)]
        internal static ContentTypeDefinition BarContentTypeDefinition;


        [Export]
        [FileExtension(".bar")]
        [ContentType("bar")]
        internal static FileExtensionToContentTypeDefinition BarFileExtensionDefinition;
    }
}
```

이전 예에서 끝나는 파일에 대 한 콘텐츠 형식 정의 만들어집니다 *.bar* 파일 확장명입니다. 이름 "bar"를 지정 하는 콘텐츠 형식 정의 하 고 **해야 합니다** 에서 파생 [CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017)합니다.

콘텐츠 형식 정의 추가한 후 다음 언어 클라이언트 클래스의 클라이언트 언어 확장을 로드 해야 할 때 정의할 수 있습니다.

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

LSP 언어 서버에 대 한 지원을 추가 하지 않아도 Visual Studio에서 사용자 고유의 프로젝트 시스템을 구현할 수 있습니다. 고객은 언어 서비스 사용을 시작 하려면 Visual Studio에서 단일 파일 또는 폴더를 열 수 있습니다. 사실, 지원 LSP 언어 서버 폴더/파일 열기 시나리오 에서만에서 작동 하도록 설계 되었습니다. 사용자 지정 프로젝트 시스템을 구현 하 고 설정과 같은 일부 기능은 작동 하지 않습니다.

## <a name="advanced-features"></a>고급 기능

### <a name="settings"></a>설정

사용자 지정 언어-서버별 설정에 대 한 지원을 사용할 수 있지만 향상 되 고 중일 것입니다. 설정은 언어 server 지원 및 일반적으로 언어 서버 데이터를 내보내는 방법을 제어 합니다. 예를 들어 언어 서버 최대 보고 된 오류에 대 한 설정이 있을 수 있습니다. 확장 작성자가 특정 프로젝트에 대해 사용자가 변경 될 수 있는 기본값을 정의 합니다.

LSP 언어 서비스 확장에 설정에 대 한 지원을 추가 하려면 아래이 단계를 수행 합니다.

1. JSON 파일을 추가 (예를 들어 *MockLanguageExtensionSettings.json*) 설정 및 기본값을 포함 하는 프로젝트에서. 예를 들면,

    ```json
    {
        "foo.maxNumberOfProblems": -1
    }
    ```
2. JSON 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 변경 된 **빌드** "콘텐츠"에 대 한 작업 및 "VSIX에 포함 ' 속성을 true로 합니다.

3. ConfigurationSections를 구현 하 고 JSON 파일에 정의 된 설정에 대 한 접두사의 목록을 반환 합니다 (Visual Studio Code에서이 매핑할 package.json에서 구성 섹션 이름):

    ```csharp
    public IEnumerable<string> ConfigurationSections
    {
        get
        {
            yield return "foo";
        }
    }
    ```

4. .Pkgdef 파일을 프로젝트에 추가 (새 텍스트 파일을 추가 하 고.pkgdef 파일 확장명이 변경). Pkgdef 파일에는이 정보를 포함 되어야 합니다.

    ```
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
    ```

    예제:
    ```
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\MockLanguageExtension]
    @="$PackageFolder$\MockLanguageExtensionSettings.json"
    ```

5. .Pkgdef 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 변경 합니다 **빌드** 작업을 **콘텐츠** 하며 **VSIX에 포함** 속성을 true로 합니다.

6. 엽니다는 *source.extension.vsixmanifest* 파일을 자산에 추가 합니다 **자산** 탭:

   ![vspackage 자산 편집](media/lsp-add-vspackage-asset.png)

   * **Type**: Microsoft.VisualStudio.VsPackage
   * **원본**: 파일 시스템의 파일
   * **경로**: [에 대 한 경로 *.pkgdef* 파일]

### <a name="user-editing-of-settings-for-a-workspace"></a>사용자의 작업 영역 설정 편집

1. 사용자는 서버를 소유 하는 파일이 포함 된 작업 영역을 엽니다.
2. 사용자의 파일을 추가 합니다 *.vs* 라는 폴더 *VSWorkspaceSettings.json*합니다.
3. 줄을 추가 하는 사용자를 *VSWorkspaceSettings.json* 파일 서버에서 제공 하는 설정에 대 한 합니다. 예를 들면,

    ```json
    {
        "foo.maxNumberOfProblems": 10
    }
    ```

### <a name="enabling-diagnostics-tracing"></a>진단 추적을 사용 하도록 설정

클라이언트와 서버 문제를 디버깅할 때 유용할 수 있는 모든 메시지를 출력 하도록 진단 추적을 사용할 수 있습니다. 진단 추적을 사용 하려면 다음을 수행 합니다.

4. 작업 영역 설정 파일을 만들거나 엽니다 *VSWorkspaceSettings.json* ("사용자의 작업 영역에 대 한 설정을 편집" 참조).
5. 설정 json 파일에 다음 줄을 추가 합니다.

```json
{
    "foo.trace.server": "Off"
}
```

추적의 자세한 정도 대 한 가능한 값을 세 가지가 있습니다.
* "꺼짐": 완전히 해제 추적
* "메시지": 추적 켜져 있지만 유일한 메서드 이름과 응답 ID를 추적 합니다.
* "Verbose": 추적 설정 전체 rpc 메시지 추적 됩니다.

파일에 기록 됩니다 추적 콘텐츠에 대해 설정 되어 있을 때 합니다 *%temp%\VisualStudio\LSP* 디렉터리입니다. 로그 명명 형식을 따릅니다 *[LanguageClientName]-[날짜/시간 스탬프].log*합니다. 현재 추적 폴더 열기 시나리오에만 사용할 수 있습니다. 언어 서버를 활성화 하는 단일 파일을 열고 추적 지원을 진단 결과는 없습니다.

### <a name="custom-messages"></a>사용자 지정 메시지

메시지 전달 및 표준 언어 서버 프로토콜의 일부분이 아닌 언어 서버에서 메시지 수신을 용이 하 게 진행에서 Api 있습니다. 사용자 지정 메시지를 처리 하려면 구현 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 언어 클라이언트 클래스의 인터페이스입니다. [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) 라이브러리 언어 클라이언트 및 서버 언어 간의 사용자 지정 메시지 전송에 사용 됩니다. 다른 Visual Studio 확장명 마찬가지로 LSP 언어 클라이언트 확장 이므로 결정할 수 있습니다 (LSP에서 지원 되지 않습니다)는 추가 기능을 추가 하려면 (다른 Visual Studio Api 사용) Visual Studio에 사용자 지정 메시지를 통해 확장 프로그램에서.

#### <a name="receiving-custom-messages"></a>사용자 지정 메시지를 수신합니다.

언어 서버에서 사용자 지정 메시지를 수신 하려면 구현 합니다 [CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017) 속성을 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 사용자 지정 메시지를 처리 하는 방법을 알고 있는 개체를 반환 하 고 . 아래 예제:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public object CustomMessageTarget
    {
        get;
        set;
    }

    public class CustomTarget
    {
        public void OnCustomNotification(JToken arg)
        {
            // Provide logic on what happens OnCustomNotification is called from the language server
        }

        public string OnCustomRequest(string test)
        {
            // Provide logic on what happens OnCustomRequest is called from the language server
        }
    }
}
```

#### <a name="sending-custom-messages"></a>사용자 지정 메시지 보내기

언어 서버에 사용자 지정 메시지를 보내도록 구현 된 [AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017) 메서드를 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)합니다. 이 메서드는 language 서버 시작 및 메시지를 받을 준비가 되 면 호출 됩니다. A [JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs) 개체가 사용 하 여 언어 서버에 메시지를 보낼 유지할 수 있습니다 매개 변수로 전달 됩니다 [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) Api. 아래 예제:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public async Task AttachForCustomMessageAsync(JsonRpc rpc)
    {
        await Task.Yield();

        this.customMessageRpc = rpc;
    }

    public async Task SendServerCustomNotification(object arg)
    {
        await this.customMessageRpc.NotifyWithParameterObjectAsync("OnCustomNotification", arg);
    }

    public async Task<string> SendServerCustomMessage(string test)
    {
        return await this.customMessageRpc.InvokeAsync<string>("OnCustomRequest", test);
    }
}
```

### <a name="middle-layer"></a>중간 계층

경우에 따라 확장 개발자는 lsp가 메시지를 보내고 언어 서버에서 받은 가로채기 하려고 합니다. 예를 들어, 확장 개발자는 특정 lsp가 메시지를 보낸 메시지 매개 변수를 변경할 수도 LSP 기능 (예: 완료)에 대 한 언어 서버에서 반환 된 결과 수정할 수 있습니다. 필요한 경우 확장 개발자 MiddleLayer API를 사용 하 여 lsp가 메시지를 가로챌 수 있습니다.

각 LSP 메시지 인터 셉 션 용 자체 중간 계층 인터페이스를 있습니다. 특정 메시지를 가로채기 위해 해당 메시지에 대 한 중간 계층 인터페이스를 구현 하는 클래스를 만듭니다. 그런 다음 구현 합니다 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 언어 클라이언트 클래스에서 인터페이스 및에서 개체의 인스턴스를 반환 합니다 [MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017) 속성입니다. 아래 예제:

```csharp
public class MockLanguageClient: ILanguageClient, ILanguageClientCustomMessage
{
    public object MiddleLayer => MiddleLayerProvider.Instance;

    private class MiddleLayerProvider : ILanguageClientWorkspaceSymbolProvider
    {
        internal readonly static MiddleLayerProvider Instance = new MiddleLayerProvider();

        private MiddleLayerProvider()
        {
        }

        public async Task<SymbolInformation[]> RequestWorkspaceSymbols(WorkspaceSymbolParams param, Func<WorkspaceSymbolParams, Task<SymbolInformation[]>> sendRequest)
        {
            // Send along the request as given
            SymbolInformation[] symbols = await sendRequest(param);

            // Only return symbols that are "files"
            return symbols.Where(sym => string.Equals(new Uri(sym.Location.Uri).Scheme, "file", StringComparison.OrdinalIgnoreCase)).ToArray();
        }
    }
}
```

중간 계층 기능은 아직 개발 중인 및 포괄적인이 아직 없습니다.

## <a name="sample-lsp-language-server-extension"></a>샘플 LSP 언어 서버 확장

Visual Studio에서 LSP 클라이언트 API를 사용 하 여 샘플 확장 프로그램의 소스 코드를 보려면 VSSDK 확장성 샘플 [LSP 샘플](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol)합니다.

## <a name="faq"></a>FAQ

**Visual Studio에서 다양 한 기능 지원을 제공 하기 위해 내 LSP 언어 서버를 보완 하기 위해 사용자 지정 프로젝트 시스템을 구축 하려는 그렇게 하는 방법에 대 한 할?**

Visual Studio 언어 LSP 기반 서버에 대 한 지원에 의존 합니다 [폴더 열기 기능](https://devblogs.microsoft.com/visualstudio/open-any-folder-with-visual-studio-15-preview/) 사용자 지정 프로젝트 시스템을 요구 하지 않도록 특별히 설계 되었습니다. 지침에 따라 사용자 고유의 사용자 지정 프로젝트 시스템을 빌드할 수 있습니다 [여기](https://github.com/Microsoft/VSProjectSystem), 하지만 설정과 같은 일부 기능은 작동 하지 않을 수 있습니다. LSP 언어 서버에 대 한 기본 초기화 논리 되므로 언어 서버 수 있으며 되도록 초기화 하는 동안 사용자 지정 논리를 제공 해야 할 수는 사용자 지정 프로젝트 시스템을 사용 하면 현재 열려 있는 폴더의 루트 폴더 위치를 전달 하는 것 제대로 시작 합니다.

**디버거 지원을 추가 하려면 어떻게 해야 하나요?**

에 대 한 지원을 제공할 예정 된 [공용 프로토콜 디버깅](https://code.visualstudio.com/docs/extensionAPI/api-debugging) 향후 릴리스에서 합니다.

**이미 VS 지원 되는 언어 서비스 설치 (예를 들어, JavaScript) 있으면 계속 설치할 수 (예: linting) 추가 기능을 제공 하는 LSP 언어 서버 확장?**

예, 하지만 일부 기능이 제대로 작동 합니다. LSP 언어 server 확장에 대 한 궁극적인 목표는 언어 서비스를 Visual Studio에서 지원 되지 않음. LSP 언어 서버를 사용 하 여 추가 지원을 제공 하는 확장 만들 수 있지만 일부 기능 (예: IntelliSense) 원활한 환경이 되지 않습니다. 일반적으로 LSP 언어 서버 확장 하지 기존 확장, 새로운 언어 환경을 제공 하는 데 사용할 수는 것이 좋습니다.

**내 완료 된 LSP 언어 서버 VSIX 게시는 무엇 인가요?**

Marketplace 지침을 참조 하세요 [여기](walkthrough-publishing-a-visual-studio-extension.md)합니다.
