---
title: 원격 디버그 시각적 개체 C++ 프로젝트 | Microsoft Docs
ms.custom: remotedebugging
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
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: fbfdb246769ac55afd7f164d91673e39e293f4c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62903526"
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>시각적 개체를 디버깅 하는 원격 C++ Visual Studio에서 프로젝트
다른 컴퓨터에 Visual Studio 응용 프로그램을 디버깅 설치 하 고 앱을 배포할 컴퓨터의 원격 도구를 실행 하려면 Visual Studio에서 원격 컴퓨터에 연결 및 다음 배포 하 고 앱을 실행 하도록 프로젝트를 구성 합니다.

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

## <a name="remote_cplusplus"></a> Visual C++ 프로젝트 원격 디버그
 다음 절차에서는 이름 및 프로젝트의 경로 C:\remotetemp\MyMfc이 고 원격 컴퓨터의 이름이 **MJO DL**합니다.

1. **mymfc**라는 MFC 애플리케이션을 만듭니다.

2. `CMainFrame::OnCreate`의 시작 부분에서 쉽게 도달할 수 있는 애플리케이션의 임의 위치(예: **MainFrm.cpp**)에 중단점을 설정합니다.

3. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 프로젝트를 마우스 **속성**합니다. **디버깅** 탭을 엽니다.

4. **실행할 디버거**를 **원격 Windows 디버거**로 설정합니다.

    ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")

5. 다음과 같이 속성을 변경합니다.

   |설정|값|
   |-|-|
   |원격 명령|C:\remotetemp\mymfc.exe|
   |작업 디렉터리|C:\remotetemp|
   |원격 서버 이름|MJO-DL:*portnumber*|
   |연결|Windows 인증을 사용한 원격|
   |디버거 형식|네이티브 전용|
   |배포 디렉터리|C:\remotetemp.|
   |배포할 추가 파일|C:\data\mymfcdata.txt.|

    추가 파일 (선택 사항)을 배포 하는 경우 두 컴퓨터 모두에서 폴더가 있어야 합니다.

6. 솔루션 탐색기에서 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **Configuration Manager**합니다.

7. **디버그** 구성의 경우 **배포** 확인란을 선택합니다.

    ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")

8. 디버깅을 시작합니다(**디버그 / 디버깅 시작** 또는 **F5**).

9. 실행 파일이 원격 컴퓨터에 자동으로 배포됩니다.

10. 메시지가 표시 되 면 원격 컴퓨터에 연결할 네트워크 자격 증명을 입력 합니다.

     필요한 자격 증명은 네트워크의 보안 구성에 적용 됩니다. 예를 들어, 도메인 컴퓨터에서 보안 인증서를 선택 하면 또는 도메인 이름 및 암호를 입력 합니다. 도메인이 아닌 컴퓨터에서 입력할 수 있습니다 컴퓨터 이름 및 유효한 사용자 계정 이름 같은 <strong>MJO-DL\name@something.com</strong>, 올바른 암호와 함께 합니다.

11. Visual Studio 컴퓨터에서 실행이 중단점에서 중지된 것이 표시됩니다.

    > [!TIP]
    > 또는 별도의 단계로 파일을 배포할 수 있습니다. **솔루션 탐색기**에서 **mymfc** 노드를 마우스 오른쪽 단추로 클릭하고 **배포**를 선택합니다.

    응용 프로그램에서 필요로 하는 비 코드 파일에 있는 경우에 지정할 수 있습니다 **배포에 추가 파일** 에 **원격 Windows 디버거** 페이지입니다.

    프로젝트에서 파일을 포함 하 고 설정할 수 또는 합니다 **콘텐츠** 속성을 **예** 에 **속성** 각 파일에 대 한 페이지입니다. 이러한 파일에 복사 됩니다는 **배포 디렉터리** 에 지정 된 된 **원격 Windows 디버거** 페이지입니다. 변경할 수도 있습니다는 **항목 형식** 하 **파일 복사** 지정 파일의 하위 폴더에 복사 해야 하는 경우 추가 속성이 있습니다 합니다 **배포 디렉터리**.

## <a name="set-up-debugging-with-remote-symbols"></a>원격 기호를 사용한 디버깅 설정

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>참고 항목
- [Visual Studio의 디버깅](../debugger/index.md)
- [디버거 소개](../debugger/debugger-feature-tour.md)
- [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)
- [원격 IIS 컴퓨터의 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)