---
title: 네트워크 기반 설치 만들기
description: 기업 내에서 Visual Studio를 배포하기 위한 네트워크 설치 지점을 만드는 방법을 알아봅니다.
ms.date: 08/06/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 4CABFD20-962E-482C-8A76-E4012052F701
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 766e3a35c6f9b775373fb7a096000177cfee131d
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870769"
---
# <a name="create-a-network-installation-of-visual-studio"></a>Visual Studio의 네트워크 설치 만들기

일반적으로 엔터프라이즈 관리자는 클라이언트 워크스테이션에 배포할 네트워크 설치 지점을 만듭니다. Visual Studio는 초기 설치에 대한 파일과 모든 제품 업데이트를 단일 폴더에 캐시할 수 있도록 설계했습니다. _레이아웃 만들기_라고도 함),

클라이언트 워크스테이션에서는 최신 제공 업데이트로 업데이트되지 않은 경우에도 설치를 관리하는 데 같은 네트워크 위치를 사용할 수 있습니다.

 > [!NOTE]
 > 엔터프라이즈 내에서 여러 버전의 Visual Studio를 사용 중인 경우(예: Visual Studio Professional과 Visual Studio Enterprise 모두 사용) 각 버전에 대한 별도의 네트워크 설치 공유를 만들어야 합니다.

## <a name="download-the-visual-studio-bootstrapper"></a>Visual Studio 부트스트래퍼 다운로드

원하는 Visual Studio 버전을 다운로드합니다. **저장**을 클릭한 다음 **폴더 열기**를 클릭합니다.

설치 실행 파일(또는 더 구체적으로 부트스트래퍼 파일)은 다음 중 하나와 일치합니다.

::: moniker range="vs-2017"

|버전 | 다운로드|
|-------------|-----------------------|
|Visual Studio Enterprise | [**vs_enterprise.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2017) |
|Visual Studio Professional | [**vs_professional.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2017) |

이 밖에 지원되는 부트스트래퍼에는 [vs_buildtools.exe](https://aka.ms/vs/15/release/vs_buildtools.exe), [vs_feedbackclient.exe](https://aka.ms/vs/15/release/vs_feedbackclient.exe), [vs_teamexplorer.exe](https://aka.ms/vs/15/release/vs_teamexplorer.exe), [vs_testagent.exe](https://aka.ms/vs/15/release/vs_testagent.exe), [vs_testcontroller.exe](https://aka.ms/vs/15/release/vs_testcontroller.exe) 및 [vs_testprofessional.exe](https://aka.ms/vs/15/release/vs_testprofessional.exe)가 있습니다.

::: moniker-end

::: moniker range="vs-2019"

|버전 | 다운로드|
|-------------|-----------------------|
|Visual Studio Enterprise | [**vs_enterprise.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2019) |
|Visual Studio Professional | [**vs_professional.exe**](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=network+install&utm_content=download+vs2019) |

이 밖에 지원되는 부트스트래퍼에는 [vs_buildtools.exe](https://aka.ms/vs/16/release/vs_buildtools.exe), [vs_teamexplorer.exe](https://aka.ms/vs/16/release/vs_teamexplorer.exe), [vs_testagent.exe](https://aka.ms/vs/16/release/vs_testagent.exe) 및 [vs_testcontroller.exe](https://aka.ms/vs/16/release/vs_testcontroller.exe)가 있습니다.

::: moniker-end

## <a name="create-an-offline-installation-folder"></a>오프라인 설치 관리자 폴더 만들기

이 단계를 완료하려면 인터넷 연결이 있어야 합니다. 모든 언어와 기능을 포함한 오프라인 설치를 만들려면 다음 예제의 명령 중 하나를 사용합니다.

   > [!IMPORTANT]
   > 전체 Visual Studio 레이아웃에는 최소 35GB의 디스크 공간이 필요하며 다운로드하는 데 약간의 시간이 걸릴 수 있습니다. 설치하려는 구성 요소만 포함하는 레이아웃을 만드는 방법은 [네트워크 레이아웃 사용자 지정](#customize-the-network-layout) 섹션을 참조하세요.
   >
   > [!TIP]
   > 다운로드 디렉터리에서 명령을 실행해야 합니다. 일반적으로 Windows 10을 실행하는 컴퓨터의 경우 `C:\Users\<username>\Downloads`입니다.

- Visual Studio Enterprise의 경우 다음을 실행합니다.

  ```vs_enterprise.exe --layout c:\vsoffline```

- Visual Studio Professional의 경우 다음을 실행합니다.

  ```vs_professional.exe --layout c:\vsoffline```

## <a name="modify-the-responsejson-file"></a>response.json 파일 수정

response.json을 수정하여 설치 프로그램이 실행될 때 사용되는 기본값을 설정할 수 있습니다.  예를 들어 자동으로 선택된 특정 워크로드 집합을 선택하도록 `response.json` 파일을 구성할 수 있습니다.
자세한 내용은 [지시 파일을 사용하여 Visual Studio 설치 자동화](automated-installation-with-response-file.md)를 참조하세요.

## <a name="copy-the-layout-to-a-network-share"></a>레이아웃을 네트워크 공유로 복사

다른 컴퓨터에서 실행될 수 있도록 레이아웃을 네트워크 공유에 호스트합니다.

다음 예제에서는 [xcopy](/windows-server/administration/windows-commands/xcopy/)를 사용합니다. 원하는 경우 [robocopy](/windows-server/administration/windows-commands/robocopy/)를 사용할 수도 있습니다.  

::: moniker range="vs-2017"

예제:

```cmd
xcopy /e c:\vsoffline \\server\products\VS2017
```

::: moniker-end

::: moniker range="vs-2019"

```cmd
xcopy /e c:\vsoffline \\server\products\VS2019
```

::: moniker-end

> [!IMPORTANT]
> 오류를 방지하려면 전체 레이아웃 경로가 80자 미만인지 확인합니다.

## <a name="customize-the-network-layout"></a>네트워크 레이아웃 사용자 지정

네트워크 레이아웃을 사용자 지정하는 데 사용할 수 있는 여러 가지 옵션이 있습니다. [언어 로캘](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales), [워크로드, 구성 요소, 권장 또는 선택적 종속성](workload-and-component-ids.md)의 특정 집합만 포함된 부분 레이아웃을 만들 수 있습니다. 워크로드의 하위 집합만 클라이언트 워크스테이션에 배포하려는 경우 이 방법이 유용할 수 있습니다. 레이아웃을 사용자 지정하기 위한 일반적인 명령줄 매개 변수는 다음과 같습니다.

* `--add` - [워크로드 또는 구성 요소 ID](workload-and-component-ids.md)를 지정합니다. <br>`--add`가 사용되면 `--add`로 지정된 워크로드 및 구성 요소만 다운로드됩니다.  `--add`를 사용하지 않으면 모든 워크로드 및 구성 요소가 다운로드됩니다.
* `--includeRecommended` - 지정된 워크로드 ID에 대한 모든 권장 구성 요소를 포함합니다.
* `--includeOptional` - 지정된 워크로드 ID에 대한 모든 권장 및 선택적 구성 요소를 포함합니다.
* `--lang` - [언어 로캘](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales)을 지정합니다.

다음은 사용자 지정 부분 레이아웃을 만드는 방법에 대한 몇 가지 예제입니다.

* 한 언어의 작업과 구성 요소를 모두 다운로드하려면 다음을 실행합니다.

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --lang en-US
    ```

* 여러 언어의 작업과 구성 요소를 모두 다운로드하려면 다음을 실행합니다.

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --lang en-US de-DE ja-JP
    ```

* 모든 언어의 작업 하나만 다운로드하려면 다음을 실행합니다.

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --add Microsoft.VisualStudio.Workload.Azure --includeRecommended
    ```

* 세 가지 언어의 작업 두 개와 선택적 구성 요소 하나를 다운로드하려면 다음을 실행합니다.

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended --lang en-US de-DE ja-JP
    ```

* 두 가지 워크로드 및 모든 권장 구성 요소를 다운로드하려면:

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended
    ```

* 두 가지 워크로드 및 모든 권장/선택적 구성 요소를 다운로드하려면 다음을 실행합니다.

    ```cmd
    vs_enterprise.exe --layout C:\vsoffline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeOptional
    ```

::: moniker range="vs-2017"

### <a name="new-in-version-153"></a>버전 15.3의 새로운 기능

::: moniker-end

::: moniker range="vs-2019"

### <a name="save-your-layout-options"></a>레이아웃 옵션 저장

::: moniker-end

레이아웃 명령을 실행할 때 지정하는 옵션(예: 워크로드 및 언어)은 저장됩니다. 후속 레이아웃 명령에는 이전 옵션이 모두 포함됩니다.  다음은 영어용 워크로드 하나만 포함된 레이아웃의 예입니다.

```cmd
vs_enterprise.exe --layout c:\VSLayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US
```

해당 레이아웃을 최신 버전으로 업데이트하려면 추가 명령줄 매개 변수를 지정할 필요가 없습니다. 이전 설정이 저장되어 이 레이아웃 폴더의 모든 후속 레이아웃 명령에 사용됩니다.  다음 명령은 기존 부분 레이아웃을 업데이트합니다.

```cmd
vs_enterprise.exe --layout c:\VSLayout
```

워크로드를 추가하려는 경우 방법은 다음 예제와 같습니다. 여기서는 Azure 워크로드와 지역화된 언어를 추가합니다.  이제 관리되는 데스크톱과 Azure가 이 레이아웃에 포함됩니다.  이러한 모든 워크로드에 대해 영어 및 독일어용 언어 리소스가 포함됩니다. 레이아웃이 사용 가능한 최신 버전으로 업데이트됩니다.

```cmd
vs_enterprise.exe --layout c:\VSLayout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE
```

기존 레이아웃을 전체 레이아웃으로 업데이트하려면 다음 예제와 같이 --all 옵션을 사용합니다.

```cmd
vs_enterprise.exe --layout c:\VSLayout --all
```

## <a name="deploy-from-a-network-installation"></a>네트워크 설치에서 배포

관리자는 설치 스크립트의 일부로 Visual Studio를 클라이언트 워크스테이션에 배포할 수 있습니다. 또는 관리자 권한을 가진 사용자는 공유에서 직접 설치 프로그램을 실행하여 Visual Studio를 컴퓨터에 설치할 수 있습니다.

* 사용자는 다음 명령을 실행하여 설치할 수 있습니다. <br>

    ```cmd
    \\server\products\VS\vs_enterprise.exe
    ```

* 관리자는 다음 명령을 실행하여 무인 모드로 설치할 수 있습니다.

    ```cmd
    \server\products\VS\vs_enterprise.exe --quiet --wait --norestart
    ```

> [!IMPORTANT]
> 오류를 방지하려면 전체 레이아웃 경로가 80자 미만인지 확인합니다.
>
> [!TIP]
> `--wait` 옵션을 배치 파일의 일부로 실행하면 `vs_enterprise.exe` 프로세스는 설치가 완료될 때까지 기다린 후에 종료 코드를 반환합니다.
>
> 엔터프라이즈 관리자가 완료된 설치에 대한 추가 작업을 수행하려는 경우(예: [성공적인 설치에 제품 키 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)) 이 방법이 유용하지만, 해당 설치에서 반환 코드를 처리하려면 설치가 완료될 때까지 기다려야 합니다.
>
> `--wait`를 사용하지 않으면 설치가 완료되기 전에 `vs_enterprise.exe` 프로세스가 종료되고 설치 작업 상태를 나타내지 않는 부정확한 종료 코드가 반환됩니다.

레이아웃에서 설치하는 경우 설치되는 콘텐츠는 레이아웃에서 가져옵니다. 그러나 레이아웃에 없는 구성 요소를 선택하면 인터넷에서 해당 구성 요소를 가져옵니다.  Visual Studio 설치 프로그램이 레이아웃에 없는 콘텐츠를 다운로드하지 못하도록 하려면 `--noWeb` 옵션을 사용합니다. `--noWeb`을 사용하고 설치하도록 선택한 콘텐츠가 레이아웃에 없으면 설치가 실패합니다.

> [!IMPORTANT]
> `--noWeb` 옵션은 Visual Studio 설치 프로그램에서 업데이트를 확인하는 과정을 허용합니다. 자세한 내용은 [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md) 페이지를 참조하세요.

### <a name="error-codes"></a>오류 코드

`--wait` 매개 변수를 사용한 경우 작업 결과에 따라 `%ERRORLEVEL%` 환경 변수는 다음 값 중 하나로 설정됩니다.

[!INCLUDE[install-error-codes-md](includes/install-error-codes-md.md)]

## <a name="update-a-network-install-layout"></a>네트워크 설치 레이아웃 업데이트

사용 가능한 제품 업데이트가 있을 경우 [네트워크 설치 레이아웃을 업데이트](update-a-network-installation-of-visual-studio.md)하여 업데이트된 패키지를 통합해야 할 수 있습니다.

## <a name="how-to-create-a-layout-for-a-previous-visual-studio-release"></a>이전 Visual Studio 릴리스에 대한 레이아웃을 만드는 방법

::: moniker range="vs-2017"

> [!NOTE]
> [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)에서 제공되는 Visual Studio 부트스트래퍼는 실행될 때마다 사용 가능한 최신 Visual Studio 릴리스를 다운로드하여 설치합니다.
>
> 따라서 오늘 Visual Studio *부트스트래퍼*를 다운로드하여 지금부터 6개월 동안 실행하면 이 부트스트래퍼를 실행하는 시점의 Visual Studio 릴리스가 설치됩니다.
>
> 그러나 *레이아웃*을 만든 다음, 설치하면 레이아웃에 있는 특정 버전의 Visual Studio가 레이아웃에 설치됩니다. 온라인에 더 새로운 버전이 있더라도 레이아웃에 있는 Visual Studio 버전이 설치됩니다.

::: moniker-end

::: moniker range="vs-2019"

> [!NOTE]
> [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)에서 제공되는 Visual Studio 부트스트래퍼는 실행될 때마다 사용 가능한 최신 Visual Studio 릴리스를 다운로드하여 설치합니다.
>
> 따라서 오늘 Visual Studio *부트스트래퍼*를 다운로드하여 지금부터 6개월 동안 실행하면 이 부트스트래퍼를 실행하는 시점의 Visual Studio 릴리스가 설치됩니다.
>
> 그러나 *레이아웃*을 만든 다음, 설치하면 레이아웃에 있는 특정 버전의 Visual Studio가 레이아웃에 설치됩니다. 온라인에 더 새로운 버전이 있더라도 레이아웃에 있는 Visual Studio 버전이 설치됩니다.

::: moniker-end

이전 버전의 Visual Studio에 대한 레이아웃을 만들어야 하는 경우 [https://my.visualstudio.com](https://my.visualstudio.com)으로 이동하여 "최종" 버전의 Visual Studio 부트스트래퍼를 다운로드합니다.

### <a name="how-to-get-support-for-your-offline-installer"></a>오프라인 설치 관리자에 대한 지원을 받는 방법

오프라인 설치에 문제가 발생하는 경우와 관련하여 자세히 알려고 합니다. [문제 보고](../ide/how-to-report-a-problem-with-visual-studio.md)를 사용하여 알리는 것이 가장 좋습니다. 이 도구를 사용하면 문제를 진단하고 해결하는 데 필요한 원격 분석과 로그를 보낼 수 있습니다.

설치 관련 문제는 [**라이브 채팅**](https://visualstudio.microsoft.com/vs/support/#talktous)(영어만 가능) 지원 옵션도 제공합니다.

사용 가능한 다른 지원 옵션도 있습니다. 목록은 [피드백](../ide/feedback-options.md) 페이지를 참조하세요.

## <a name="see-also"></a>참고 항목

- [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
- [Visual Studio의 네트워크 기반 설치 업데이트](update-a-network-installation-of-visual-studio.md)
- [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)
- [Visual Studio 제품 수명 주기 및 서비스](/visualstudio/releases/2019/servicing/)
- [서비스 기준선에서 Visual Studio 업데이트](update-servicing-baseline.md)
- [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
- [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)
