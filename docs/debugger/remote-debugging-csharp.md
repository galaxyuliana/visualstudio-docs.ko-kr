---
title: 원격 디버그 C# 또는 VB 프로젝트 | Microsoft Docs
ms.custom:
- remotedebugging"=
- seodec18
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: a9753fbb-e7f4-47f0-9dbe-9de90c6c8457
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4c646f8f6dc228d42d6efb5ec44f3ec19a53a551
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408530"
---
# <a name="remote-debugging-a-c-or-visual-basic-project-in-visual-studio"></a>Visual Studio에서 C# 또는 Visual Basic 프로젝트 원격 디버그
다른 컴퓨터에 배포 된 Visual Studio 응용 프로그램을 디버깅 하려면 설치 하 고 앱을 배포한 컴퓨터에서 원격 도구를 실행, Visual Studio에서 원격 컴퓨터에 연결 하도록 프로젝트를 구성 및 응용 프로그램을 실행 합니다.

![원격 디버거 구성 요소](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

원격 디버깅 유니버설 Windows 앱 (UWP)에 대 한 정보를 참조 하세요 [설치 된 앱 패키지 디버그](debug-installed-app-package.md)합니다.

## <a name="requirements"></a>요구 사항

원격 디버거는 Windows 7에서 지원 되며 최신 (phone 있는 경우) 및 Windows Server 2008 서비스 팩 2부터 Windows Server의 버전입니다. 요구 사항의 전체 목록은 참조 하세요 [요구 사항](../debugger/remote-debugging.md#requirements_msvsmon)합니다.

> [!NOTE]
> 프록시를 통해 연결 하는 두 컴퓨터 간에 디버깅이 지원 되지 않습니다. 국가 간 높은 대기 시간 또는 낮은 대역폭 연결에서는 인터넷에 접속 등을 통해 또는 인터넷을 통해 디버깅 권장 되지 않습니다 및 실패 하거나 느리고 수 있습니다.

## <a name="download-and-install-the-remote-tools"></a>원격 도구 다운로드 및 설치

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> 일부 시나리오에서는 파일 공유에서 원격 디버거를 실행 하는 것이 가장 효율적일 수 있습니다. 자세한 내용은 [파일 공유에서 원격 디버거 실행](../debugger/remote-debugging.md#fileshare_msvsmon)합니다.

## <a name="BKMK_setup"></a> 원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 추가 사용자에 대 한 사용 권한을 추가 하는 인증 모드를 변경 하거나 원격 디버거의 포트 번호에 필요한 경우 참조 [원격 디버거 구성](../debugger/remote-debugging.md#configure_msvsmon)합니다.

## <a name="remote_csharp"></a> 프로젝트 원격 디버그
디버거는 원격 컴퓨터에 Visual C# 또는 Visual Basic 데스크톱 응용 프로그램을 배포할 수 없지만 다음과 같이 원격으로 계속 디버그할 수 있습니다. 다음 절차 라는 컴퓨터에서 디버깅 하 려 한다고 가정 **MJO DL**아래 그림에 나와 있는 것 처럼 합니다.

1. **MyWpf**라는 WPF 프로젝트를 만듭니다.

2. 쉽게 도달할 수 있는 코드의 임의 위치에 중단점을 설정합니다.

    예를 들어 단추 처리기에 중단점을 설정할 수 있습니다. 이렇게 하려면 MainWindow.xaml을 엽니다 도구 상자에서 단추 컨트롤을 추가 하 고 해당 처리기를 열려면 단추를 두 번 클릭 합니다.

3. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

4. **속성** 페이지에서 **디버그** 탭을 선택합니다.

    ![RemoteDebuggerCSharp](../debugger/media/remotedebuggercsharp.png "RemoteDebuggerCSharp")

5. **작업 디렉터리** 텍스트 상자가 비어 있는지 확인합니다.

6. 선택 **사용 하 여 원격 컴퓨터**, 유형과 **yourmachinename:port** 텍스트 상자에 있습니다. (포트 번호는 원격 디버거 창에 표시 됩니다. 포트 번호를 증가 시킵니다 Visual Studio의 각 버전에는 2를).

    이 예제에서는 다음을 사용 합니다.
    ::: moniker range=">=vs-2019"
    **MJO-DL:4024** Visual Studio 2019에
    ::: moniker-end
    ::: moniker range="vs-2017"
    **MJO-DL:4022** Visual Studio 2017에서
    ::: moniker-end

7. **네이티브 코드 디버깅 사용**이 선택되지 않았는지 확인합니다.

8. 프로젝트를 빌드합니다.

9. Visual Studio 컴퓨터의 **Debug** 폴더와 동일한 경로인 폴더를 원격 컴퓨터에 만듭니다(**\<source path>\MyWPF\MyWPF\bin\Debug**).

10. Visual Studio 컴퓨터에서 방금 빌드한 실행 파일을 원격 컴퓨터에서 새로 만든 폴더에 복사합니다.

    > [!CAUTION]
    > 코드를 다시 작성을 변경 하지 마세요 (또는이 단계를 반복 해야 합니다). 원격 컴퓨터에 복사한 실행 파일은 로컬 소스 및 기호와 정확히 일치해야 합니다.

    프로젝트를 수동으로 복사, Xcopy, Robocopy, Powershell 또는 다른 옵션을 사용할 수 있습니다.

11. 원격 디버거가 대상 컴퓨터에서 실행 되 고 있는지 (없는 경우 검색 **원격 디버거** 에 **시작** 메뉴). 원격 디버거 창에는 다음과 같습니다.

     ![RemoteDebuggerWindow](../debugger/media/remotedebuggerwindow.png "RemoteDebuggerWindow")

12. Visual Studio에서 디버깅을 시작합니다(**디버그 > 디버깅 시작** 또는 **F5** 키).

13. 메시지가 표시 되 면 원격 컴퓨터에 연결할 네트워크 자격 증명을 입력 합니다.

     필요한 자격 증명은 네트워크의 보안 구성에 따라 달라 집니다. 예를 들어, 도메인 컴퓨터에서 도메인 이름 및 암호를 입력할 수 있습니다. 도메인이 아닌 컴퓨터에서 입력할 수 있습니다 컴퓨터 이름 및 유효한 사용자 계정 이름 같은 <strong>MJO-DL\name@something.com</strong>, 올바른 암호와 함께 합니다.

     WPF 애플리케이션의 주 창이 원격 컴퓨터에서 열려 있다고 표시됩니다.

14. 필요한 경우 중단점을 적중 하려면 작업을 수행 합니다. 중단점이 활성화된 것으로 표시되어야 합니다. 활성화되지 않은 경우 애플리케이션에 대한 기호가 로드되지 않은 것입니다. 다시 시도 및에서 문제를 해결 하는 방법 및 기호를 로드 하는 방법에 대 한 정보를 제공 하는 작동 하지 않으면 [기호 파일 이해 및 Visual Studio의 기호 설정](https://devblogs.microsoft.com/devops/understanding-symbol-files-and-visual-studios-symbol-settings/)합니다.

15. Visual Studio 컴퓨터에서 실행이 중단점에서 중지된 것이 표시됩니다.

    응용 프로그램에서 사용 해야 하는 모든 비 코드 파일에 있는 경우 Visual Studio 프로젝트에 포함 해야 합니다. 추가 파일을 위한 프로젝트 폴더를 만듭니다(**솔루션 탐색기**에서 **추가 > 새 폴더** 클릭). 그런 다음, 폴더에 파일을 추가합니다(**솔루션 탐색기**에서 **추가 / 기존 항목**을 클릭한 다음, 파일 선택). 각 파일에 대한 **속성** 페이지에서 **출력 디렉터리에 복사**를 **항상 복사**로 설정합니다.

## <a name="set-up-debugging-with-remote-symbols"></a>원격 기호를 사용한 디버깅 설정

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>참고 항목
- [Visual Studio의 디버깅](../debugger/index.md)
- [디버거 소개](../debugger/debugger-feature-tour.md)
- [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)
- [원격 IIS 컴퓨터의 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)