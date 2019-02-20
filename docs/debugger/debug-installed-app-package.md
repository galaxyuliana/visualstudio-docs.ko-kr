---
title: 설치 된 UWP 앱 패키지 디버그 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/07/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 84d2296a467bb1fc2c3e1466b715578c94c7d0d8
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317940"
---
# <a name="debug-an-installed-uwp-app-package-in-visual-studio"></a>Visual Studio에서 설치 된 UWP 앱 패키지 디버그

Visual Studio는 Xbox, HoloLens, IoT 장치와 Windows 10 컴퓨터에 설치 된 유니버설 Windows 플랫폼 (UWP) 앱 패키지를 디버깅할 수 있습니다.

>[!NOTE]
>Visual Studio 설치 된 UWP 앱에 대 한 디버깅 휴대폰에서 지원 되지 않습니다.
   
UWP 앱을 디버깅 하는 방법에 대 한 자세한 내용은 블로그 게시물을 참조 [설치 된 앱 패키지를 디버깅](https://devblogs.microsoft.com/devops/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) 하 고 [유니버설 Windows 앱 (UWP) 빌드](https://devblogs.microsoft.com/visualstudio/universal-windows-apps-targeting-windows-10-anniversary-sdk/)합니다.

## <a name="debug-an-installed-uwp-app-on-a-local-machine"></a>로컬 컴퓨터에 설치 된 UWP 앱 디버그

1. Visual Studio에서 선택 **디버깅할** > **기타 디버그 대상** > **디버그 Installed App Package**합니다.

1. 에 **디버그 Installed App Package** 대화 상자 아래에 있는 **연결 형식**를 선택 **로컬 컴퓨터**합니다.

1. 아래 **앱 패키지 설치**디버그 하려는 앱을 선택 하거나 검색 상자에 해당 이름을 입력 합니다. 비-실행 중인 설치 된 응용 프로그램 패키지 아래에 나타납니다 **실행 되 고 있지**, 및 앱을 실행 중인 **실행**합니다.

   ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

1. 필요한 경우 아래에 있는 코드 형식을 변경할 **다음 코드 형식 디버깅**, 다른 옵션을 선택 합니다.
   - 선택 **시작 하지 않음 시작 시 코드를 디버그** 앱 시작 시 디버깅을 시작 합니다. 제어 경로에서 디버그 하는 효과적인 방법을 앱이 시작 되는 경우 디버깅 시작 [다른 시작 방법](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

1. 선택 **시작**, 앱을 실행 중인 경우 누르거나 **연결**합니다.

> [!NOTE]
> 선택 하 여 모든 실행 중인 UWP 또는 다른 응용 프로그램 프로세스에 첨부할 수도 있습니다 **디버깅할** > **프로세스에 연결** Visual Studio에서. 원래 Visual Studio 프로젝트를 실행 중인 프로세스에 연결할 필요는 없지만 응용 프로그램의 기호를 로드 하는 데 도움이 됩니다 크게 원본 코드 없는 프로세스를 디버깅 하는 경우. 참조 [디버거에서 기호 및 소스 파일 지정](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다.

## <a name="remote"></a> 원격 컴퓨터 또는 장치에 설치 된 UWP 앱 디버그

처음으로 Visual Studio Windows 10 장치 또는 원격 post-크리에이터 업데이트가 Windows 10 컴퓨터에 설치 된 UWP 앱 디버그 대상 장치에서 원격 디버깅 도구를 설치 합니다.

1. [개발자 모드를 사용 하도록 설정](/windows/uwp/get-started/enable-your-device-for-development) Visual Studio 컴퓨터와 원격 장치 또는 컴퓨터에 있습니다.

1. Pre-크리에이터 업데이트가 Windows 10을 실행 하는 원격 컴퓨터에 연결 하는 경우 [수동으로 설치 하 고 원격 디버거 시작](../debugger/remote-debugging.md) 원격 컴퓨터.

1. Visual Studio 컴퓨터에서 선택 **디버깅할** > **기타 디버그 대상** > **디버그 Installed App Package**합니다.

1. 에 **디버그 Installed App Package** 대화 상자 아래에 있는 **연결 형식**를 선택 **원격 컴퓨터** 또는 **장치**합니다.

   선택 하는 경우 **장치**, Windows 10 장치에 컴퓨터를 물리적으로 연결 해야 합니다.

   컴퓨터 주소 옆에 표시 되지 않는 경우 원격 컴퓨터에 대 한 **주소**를 선택 **변경**합니다.

   1. 에 **원격 연결** 대화 상자에서 다음 **주소**, 이름 또는 연결 하려는 컴퓨터의 IP 주소를 입력 합니다.

      ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

      디버거에서 컴퓨터 이름을 사용 하 여 원격 컴퓨터에 연결할 수 없는 경우 IP 주소를 대신 사용 합니다. Xbox, HoloLens, IoT 장치에 대 한 IP 주소를 사용 합니다.
   1. 다음 인증 옵션 선택 **인증 모드**합니다.

      대부분의 앱에 대 한 기본값을 유지 **유니버설 (암호화 되지 않은 프로토콜)** 합니다.
   1. 선택 **선택**합니다.

1. 아래 **앱 패키지 설치**디버그 하려는 앱을 선택 하거나 검색 상자에 해당 이름을 입력 합니다. 비-실행 중인 설치 된 응용 프로그램 패키지 아래에 나타납니다 **실행 되 고 있지**, 및 앱을 실행 중인 **실행**합니다.

1. 필요한 경우 아래에 있는 코드 형식을 변경할 **다음 코드 형식 디버깅**, 다른 옵션을 선택 합니다.
   - 선택 **시작 하지 않음 시작 시 코드를 디버그** 앱 시작 시 디버깅을 시작 합니다. 제어 경로에서 디버그 하는 효과적인 방법을 앱이 시작 되는 경우 디버깅 시작 [다른 시작 방법](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

1. 선택 **시작**, 앱을 실행 중인 경우 누르거나 **연결**합니다.

처음으로 연결된 된 Xbox, HoloLens, IoT 장치에서 설치 된 앱 패키지를 디버깅을 시작 하면 Visual Studio는 올바른 버전의 대상 장치에 대해 원격 디버거를 설치 합니다. 상당한 시간과 메시지 걸릴 수 있습니다 원격 디버거 설치 **원격 디버거를 시작** 진행 중일 때 표시 됩니다.

>[!NOTE]
>현재, Xbox 또는 HoloLens 장치를 다시 디버거가 이미 실행 중인 경우 연결 된 앱을 시작 합니다.

UWP 앱의 원격 배포에 대 한 자세한 내용은 참조 하세요. [UWP 앱을 배포 및 디버그](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options) 하 고 [원격 컴퓨터에서 디버그 하는 UWP 앱](run-windows-store-apps-on-a-remote-machine.md)합니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio의 디버깅](../debugger/index.md)
- [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
- [원격 디버깅](../debugger/remote-debugging.md)
- [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)
- [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)