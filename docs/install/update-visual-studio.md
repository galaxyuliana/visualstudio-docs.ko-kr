---
title: Visual Studio 업데이트
titleSuffix: ''
description: 가장 최신 릴리스로 Visual Studio를 업데이트하는 방법을 단계별로 알아봅니다.
ms.date: 04/23/2018
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- update Visual Studio
- change visual studio
- changing Visual Studio
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a8e972c86f4a3dfecdcd36d2aec768e0ea3b0065
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953960"
---
# <a name="update-visual-studio-2017-to-the-most-recent-release"></a>Visual Studio 2017을 최신 릴리스 버전으로 업데이트

항상 최신 기능, 수정 사항 및 개선 사항을 얻을 수 있도록 [최신 버전](/visualstudio/releasenotes/vs2017-relnotes)의 Visual Studio 2017로 업데이트하는 것이 좋습니다.

릴리스 전에 체험해 보려면 다음 버전의 [미리 보기 릴리스](/visualstudio/releasenotes/vs2017-preview-relnotes)를 다운로드하는 것도 좋습니다.

> [!IMPORTANT]
> Visual Studio를 설치, 업데이트 또는 수정하려면 관리 권한이 있는 계정으로 로그온해야 합니다. 자세한 내용은 [사용자 권한 및 Visual Studio](../ide/user-permissions-and-visual-studio.md)를 참조하세요.

> [!NOTE]
> 이 토픽은 Windows의 Visual Studio에 적용됩니다. Mac용 Visual Studio는 [Mac용 Visual Studio 업데이트](/visualstudio/mac/update)를 참조하세요.

## <a name="update-visual-studio-2017-version-156-or-later"></a>Visual Studio 2017 버전 15.6 이상 업데이트

IDE 내에서 바로 사용하기 쉽도록 설치 및 업데이트 환경이 간소화되었습니다. 버전 15.6 이상에서 최신 버전의 Visual Studio로 업데이트하는 방법은 다음과 같습니다.

### <a name="use-the-notifications-hub"></a>알림 허브 사용

업데이트가 있으면 Visual Studio에 해당 알림 플래그가 있습니다.

1. 작업을 저장합니다.

2. 알림 플래그를 선택하여 **알림** 허브를 열고 설치할 업데이트를 선택합니다.

   ![알림 허브를 사용하여 Visual Studio 2017 업데이트](media/vs-install-notifications-hub-15dot6.png "Visual Studio 2017의 알림 허브")

3. **업데이트** 대화 상자가 열리면 **지금 업데이트**를 선택합니다.

    ![알림 허브의 업데이트 대화 상자를 사용하여 Visual Studio 2017 업데이트](media/vs-update-now-from-notifications-hub.png "Visual Studio 알림 허브의 업데이트 대화 상자")

     사용자 액세스 제어 대화 상자가 열리면 **예**를 선택합니다. “잠시 기다려 주세요.” 대화 상자가 잠시 열릴 수 있으며, 그런 다음, Visual Studio 설치 관리자가 열려 업데이트를 시작합니다.

     ![버전 15.6의 새 Visual Studio 설치 관리자 환경](media/visual-studio-15dot6-installer.png "버전 15.6의 새 Visual Studio 설치 관리자 환경")

     업데이트가 계속됩니다. 업데이트가 완료되면 Visual Studio가 다시 시작됩니다.

     > [!NOTE]
     > Visual Studio를 관리자 모드로 실행하는 경우에는 업데이트 후 Visual Studio를 수동으로 다시 시작해야 합니다.

### <a name="use-the-ide"></a>IDE 사용

업데이트를 확인한 다음, Visual Studio의 메뉴 표시줄에서 업데이트를 설치할 수 있습니다.

1. 작업을 저장합니다.

2. **도움말** > **업데이트 확인**을 선택합니다.

     ![Visual Studio 버전 15.6의 새 도움말 메뉴](media/vs-help-menu-check-for-updates.png "Visual Studio 버전 15.6의 새 도움말 메뉴")

3. **업데이트** 대화 상자가 열리면 **지금 업데이트**를 선택합니다.

   이전 섹션에서 설명한 대로 업데이트가 진행되고, 업데이트가 완료되면 Visual Studio가 다시 시작됩니다.

   > [!NOTE]
   > Visual Studio를 관리자 모드로 실행하는 경우에는 업데이트 후 Visual Studio를 수동으로 다시 시작해야 합니다.

### <a name="use-the-visual-studio-installer"></a>Visual Studio 설치 관리자 사용

이전 버전의 Visual Studio 2017과 마찬가지로, Visual Studio 설치 관리자를 사용하여 업데이트를 설치할 수 있습니다.

1. 작업을 저장합니다.

2. 설치 관리자를 엽니다. 계속하기 전에 Visual Studio 설치 관리자를 업데이트해야 할 수도 있습니다.

   > [!NOTE]
   > Windows 10을 실행하는 컴퓨터에서는 **V** 문자 아래에 **Visual Studio 설치 관리자**로 설치 관리자가 나타나거나, **M** 문자 아래에 **Microsoft Visual Studio 설치 관리자**로 나타납니다.

3. 설치 관리자의 **제품** 페이지에서 사용자가 설치한 Visual Studio의 버전을 확인합니다.

4. 업데이트를 사용할 수 있는 경우 **업데이트** 단추가 표시됩니다. (설치 관리자가 업데이트를 사용할 수 있는지 여부를 확인하는 데 몇 초 정도 걸릴 수 있습니다.)

   **업데이트** 단추를 선택하여 업데이트를 설치합니다.

     ![Visual Studio 설치 관리자를 사용하여 Visual Studio 2017 업데이트](media/update-visual-studio.png "Visual Studio 설치 관리자를 사용하여 Visual Studio 2017 업데이트")

## <a name="update-visual-studio-2017-version-155-or-earlier"></a>Visual Studio 2017 버전 15.5 또는 이전 버전 업데이트

이전 버전을 사용하는 경우 Visual Studio 2017 버전 15.0 - 버전 15.5에서 업데이트를 적용하는 방법은 다음과 같습니다.

### <a name="update-by-using-the-notifications-hub"></a>알림 허브를 사용하여 업데이트

1. 업데이트가 있으면 Visual Studio에 해당 알림 플래그가 있습니다.

   ![알림 허브를 사용하여 Visual Studio 2017 업데이트](media/notification-flag.png "Visual Studio의 업데이트 알림 플래그")

   알림 플래그를 선택하여 **알림** 허브를 엽니다.

   ![알림 허브를 사용하여 Visual Studio 2017 업데이트](media/notifications-hub.png "Visual Studio의 알림 허브")

2. **“Visual Studio 업데이트” 사용 가능**을 선택하여 **확장 및 업데이트** 대화 상자를 엽니다.

   ![알림 허브를 사용하여 Visual Studio 2017 업데이트](media/notifications-hub-select.png "Visual Studio의 알림 허브")

3. **확장 및 업데이트** 대화 상자에서 **업데이트** 단추를 선택합니다.

   ![알림 허브를 사용하여 Visual Studio 2017 업데이트](media/notifications-extensions-and-updates.png "Visual Studio의 확장 및 업데이트 대화 상자")

#### <a name="more-about-visual-studio-notifications"></a>Visual Studio 알림 상세 정보

Visual Studio는 Visual Studio 자체나 구성 요소에 사용 가능한 업데이트가 있을 때와, Visual Studio 환경에서 특정 이벤트가 발생했을 때 이를 사용자에게 알립니다.

* 알림 플래그가 노랑이면 설치할 수 있는 Visual Studio 제품 업데이트가 있다는 것입니다.
* 알림 플래그 빨강이면 라이선스에 문제가 있습니다.
* 알림 플래그가 검정이면 확인이 필요한 선택적 또는 정보 메시지가 있습니다.

알림 플래그를 선택하여 **알림** 허브를 열고 조치할 알림을 선택합니다. 또는 알림을 무시하거나 해제합니다.

 ![알림 허브의 선택적 또는 정보 메시지 보기](media/notification-flag-optional.png "Visual Studio의 선택적 또는 정보 메시지 알림 플래그")

알림을 무시하도록 선택한 경우 Visual Studio에서 알림 표시를 중지합니다. 무시된 알림 목록을 다시 설정하려면 알림 허브에서 **설정** 단추를 선택합니다.

   ![알림 허브에서 설정 단추를 선택하여 알림 옵션 보기](media/vs-notifications-hub-settings-button.png "알림 허브에서 설정 단추를 선택하여 알림 옵션 보기")

### <a name="update-by-using-the-visual-studio-installer"></a>Visual Studio 설치 관리자를 사용하여 업데이트

1. 설치 관리자를 엽니다. 계속하기 전에 설치 관리자를 업데이트해야 할 수 있습니다. 이 경우 업데이트하라는 메시지가 나타납니다.

   > [!NOTE]
   > Windows 10을 실행하는 컴퓨터에서는 **V** 문자 아래에 **Visual Studio 설치 관리자**로 설치 관리자가 나타나거나, **M** 문자 아래에 **Microsoft Visual Studio 설치 관리자**로 나타납니다.

2. 설치 관리자의 **제품** 페이지에서 사용자가 설치한 Visual Studio의 버전을 확인합니다.

3. 업데이트를 사용할 수 있는 경우 **업데이트** 단추가 표시됩니다. (설치 관리자가 업데이트를 사용할 수 있는지 여부를 확인하는 데 몇 초 정도 걸릴 수 있습니다.)

   **업데이트** 단추를 선택하여 업데이트를 설치합니다.

     ![Visual Studio 설치 관리자를 사용하여 Visual Studio 2017 업데이트](media/update-visual-studio.png "Visual Studio 설치 관리자를 사용하여 Visual Studio 2017 업데이트")

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 수정](modify-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
* [Mac용 Visual Studio 업데이트](/visualstudio/mac/update)