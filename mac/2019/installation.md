---
title: Mac용 Visual Studio 2019 미리 보기 설치
description: Mac용 Visual Studio 2019 미리 보기 및 플랫폼 간 개발에 필요한 추가 구성 요소를 설치하는 방법에 대한 지침입니다.
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: acd8f3bc4f5fefa0a0c8b273856579067fb33c6a
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54315901"
---
# <a name="install-visual-studio-2019-for-mac-preview"></a>Mac용 Visual Studio 2019 미리 보기 설치

> [!NOTE]
> Mac용 Visual Studio 2019 미리 보기는 안정적인 Mac용 Visual Studio 릴리스와 함께 설치할 수 있습니다. 설치하는 동안 안정적인 최신 버전이 아닌 경우 기존 Visual Studio를 업데이트하라는 메시지가 표시됩니다.

## <a name="requirements-for-the-visual-studio-2019-for-mac-preview"></a>Mac용 Visual Studio 2019 미리 보기의 요구 사항

- macOS Sierra 10.13 이상이 설치된 Mac

iOS 또는 macOS용 Xamarin 앱을 빌드하려면 다음 항목도 필요합니다.

- Xcode 10.0 이상 대개 안정적인 최신 버전을 사용하는 것이 좋습니다.
- Apple ID. Apple ID가 없으면 https://appleid.apple.com 에서 새로 만들 수 있습니다. Xcode를 설치하고 서명하려면 Apple ID가 있어야 합니다.

## <a name="installing-the-preview"></a>미리 보기 설치

1. [Mac용 Visual Studio 미리 보기 페이지](https://aka.ms/vs4mac-preview)에서 미리 보기 설치 관리자를 다운로드합니다.
2. 다운로드가 완료되면 **VisualStudioforMacPreviewInstaller.dmg**를 클릭하여 설치 관리자를 탑재한 다음, 화살표 로고를 두 번 클릭하여 설치 관리자를 실행합니다.

    [![설치를 시작하려면 큰 화살표를 클릭](media/install-preview-installer-sml.png)](media/install-preview-installer.png#lightbox)

3. 인터넷에서 애플리케이션이 다운로드된다는 경고가 표시될 수 있습니다. **열기**를 클릭합니다.
4. 설치 관리자가 시스템을 확인할 때까지 기다립니다.

    [![설치 관리자가 구성 요소를 설치할 시스템 확인](media/install-preview-checking-sml.png)](media/install-preview-checking.png#lightbox)

5. 개인 정보 및 라이선스 조건에 동의하라는 경고가 나타납니다. 링크가 안내하는 문서를 잘 읽고, 동의하면 **계속**을 누릅니다.

    [![개인 정보 및 조건 링크를 클릭한 다음, 동의하면 계속 진행](media/install-preview-privacy-sml.png)](media/install-preview-privacy.png#lightbox)

6. 사용 가능한 워크로드 목록이 표시됩니다. 사용할 워크로드를 선택합니다.

    [![설치할 워크로드 기능 선택](media/install-preview-selection-sml.png)](media/install-preview-selection.png#lightbox)

    현재 사용하는 Mac용 Visual Studio 2017 버전이 7.7보다 낮으면 안정적인 최신 버전(병렬 설치를 지원하려면 필요)으로 업그레이드하는 것을 승인해 달라는 메시지가 나타납니다. **계속**을 눌러 업그레이드를 승인합니다.

    ![안정적인 버전 7.7로 업그레이드 필요](media/install-preview-older-upgrade.png)

7. 원하는 항목을 선택한 후 **설치** 단추를 누릅니다.
8. 설치 관리자는 Mac용 Visual Studio 및 사용자가 선택한 워크로드를 다운로드하고 설치하는 동안 진행률을 표시합니다. 설치에 필요한 권한을 부여하려면 암호를 입력하라는 메시지가 표시될 수 있습니다.
9. 언제든지 미리 보기 버전을 테스트하고 싶을 때 **Visual Studio(미리 보기)** 를 사용하거나, 프로덕션 작업에 필요한 안정적인 최신 Visual Studio로 다시 전환할 수 있습니다. 다음 두 아이콘이 여기에 표시됩니다.

    ![안정적인 버전과 미리 보기 아이콘의 차이점](media/install-preview-icons-sml.png)

회사 환경에 설치하는 동안 네트워크 문제가 있는 경우 [방화벽 또는 프록시 뒤에 설치](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server) 지침을 검토하세요.

[릴리스 정보](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-preview-relnotes)의 변경 내용에 대해 자세히 알아보세요.

> [!NOTE]
> 원래 설치 중 6단계에서 선택 취소하여 플랫폼 또는 도구를 설치하지 않도록 선택한 경우 나중에 구성 요소를 추가하려면 설치 관리자를 다시 실행해야 합니다.

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>방화벽 또는 프록시 서버 뒤에 Mac용 Visual Studio 설치

방화벽 뒤에 있는 Mac용 Visual Studio를 설치하려면 소프트웨어에 필요한 도구 및 업데이트의 다운로드를 허용하기 위해 일부 엔드포인트에 액세스가 가능해야 합니다.

다음 위치에 액세스할 수 있도록 네트워크를 구성합니다.

- [Visual Studio 엔드포인트](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>다음 단계

Mac용 Visual Studio를 설치하면 앱 코드 작성을 시작할 수 있습니다. 다음 가이드에서는 프로젝트를 작성 및 배포하는 다음 단계를 안내합니다.

### <a name="ios"></a>iOS

1. [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [장치 프로비저닝](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(장치에서 애플리케이션을 실행하려면).

### <a name="android"></a>Android

1. [Xamarin Android SDK Manager 사용](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Android SDK 에뮬레이터](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [개발용 디바이스 설정](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>.NET Core 앱, ASP.NET Core 웹앱, Unity 게임 개발

다른 워크로드의 경우 [워크로드](/visualstudio/mac/workloads) 페이지를 참조하세요.

## <a name="see-also"></a>참고 항목

- [Visual Studio 2017 설치(Windows에서)](/visualstudio/install/install-visual-studio)
