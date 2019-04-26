---
title: Visual Studio 구독에 라이선스 할당 | Microsoft Docs
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 07/16/2018
ms.topic: conceptual
description: 관리자가 구독자에게 라이선스를 할당하는 방법을 알아봅니다.
searchscope: VS Subscription
ms.openlocfilehash: 97962571d8a7c433a5f72af90d9107f9e2b08a9b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946517"
---
# <a name="assign-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio 구독 관리자 포털에서 라이선스 할당

Visual Studio 구독 관리자는 관리자 포털을 사용하여 개별 사용자 또는 사용자 그룹에 구독을 할당할 수 있습니다.

사용자 그룹의 경우 한 번에 하나씩 구독을 할당하거나 **대량 추가** 기능을 사용하여 구독자 목록 및 해당 구독 정보를 쉽고 빠르게 업로드할 수 있습니다.

## <a name="individual-assignments"></a>개별 할당

구독 혜택에 액세스할 수 있도록 새 사용자에게 Visual Studio 구독 라이선스를 할당하는 방법은 다음과 같습니다.

1. [관리자 포털](https://manage.visualstudio.com)에 로그인합니다.

2. 단일 Visual Studio 구독자에게 라이선스를 할당하려면 테이블 위쪽에서 **추가**를 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![단일 구독자 추가](media/add-single-subscriber.png)

3. 새 구독자에 대한 정보를 양식 필드에 입력합니다. 조직에서 Azure Active Directory를 사용하는 경우 이 필드는 현재 디렉터리에 있는 사람을 찾는 검색 기능 역할을 하므로 검색 결과에서 올바른 사용자를 선택할 수 있습니다. 해당 사용자를 선택한 후에 사용자의 이름, 로그인 이메일 및 알림 이메일이 자동으로 채워집니다.
   > [!div class="mx-imgBorder"]
   > ![새 알림 이메일 주소 추가](media/add-new-subscriber-notification-email.png)

    구독자가 [Visual Studio 구독 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에 로그인할 때 소프트웨어 다운로드에 액세스할 수 있도록 하려면 **다운로드 설정**에서 다운로드 토글을 사용하도록 설정된 상태로 둡니다. 다운로드를 사용하지 않도록 선택하면 사용자는 소프트웨어 다운로드에 액세스할 수 없지만 구독에 포함된 다른 모든 혜택에는 계속 액세스할 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![다운로드 액세스 권한](media/access-to-downloads.png)

    구독자가 정보를 수신하는 언어를 변경하려는 경우 **통신 기본 설정** 섹션에서 수행할 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![알림 이메일을 보낼 때 사용할 언어 변경](media/change-subscriber-communication-preference.png)

    구독에 고유한 참조 정보를 추가하려는 경우 **참조 추가** 섹션에서 수행할 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![각 구독에 고유한 참조 정보 추가](media/add-subscriber-reference-notes.png)

    옵션 선택 및 구독자에 대한 데이터 입력을 완료한 경우 **구독자 추가** 플라이아웃 맨 아래에 **추가**를 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![추가 단추 선택](media/add-button.png)

4. 구독자가 추가되면 새 구독자에게 추가 지침이 있는 할당 이메일을 자동으로 보냅니다. 구독자를 선택하고 위쪽 메뉴의 **다시 보내기** 단추를 클릭하여 할당 전자 메일을 다시 보낼 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![필요한 때마다 활성화 이메일을 모든 사용자 또는 여러 사용자에게 다시 보내기](media/resend-subscriber-activation-emails.png)

## <a name="bulk-assignments"></a>대량 할당

1. 여러 구독자를 한 번에 추가하려면 **구독자 관리** 탭으로 이동합니다. 맨 위에 있는 리본에서 **대량 추가**를 클릭합니다.
   > [!div class="mx-imgBorder"]
   > ![여러 구독자 추가](media/add-multiple-subscribers.png)

2. 대량 할당은 Microsoft Excel 템플릿을 사용하여 구독자를 업로드합니다. [여러 구독자 업로드] 대화 상자에서 **다운로드**를 클릭하여 템플릿을 다운로드합니다.
   > [!div class="mx-imgBorder"]
   > ![Excel 템플릿을 다운로드하여 여러 구독자 업로드](media/download-template-upload-subscribers.png)
   >
   > [!NOTE]
   > 항상 이 템플릿의 최신 버전을 다운로드합니다. 이전 버전을 사용하는 경우 대량 업로드가 실패할 수 있습니다.

3. Excel 스프레드시트에서 구독을 할당하려는 개인에 대한 정보로 필드를 채웁니다. (*참조*는 선택적 필드입니다.) 작업을 마친 후에 파일을 로컬로 저장합니다.

   원활한 업로드를 보장하기 위해 다음 모범 사례를 관찰합니다.

    - 양식 필드에 쉼표가 없는지 확인합니다.
    - 양식 필드 앞뒤의 공백을 제거합니다.
    - 두 부분으로 이루어진 사용자 이름에서 첫 번째 이름과 마지막 이름 사이에 여분의 공백이 포함되지 않아야 합니다(예: 사용자의 첫 번째 이름이 "Maggie May"와 같이 두 부분으로 이루어진 경우 시스템에서 여분의 공백을 제거하지 않으므로 "MaggieMay"로 입력해야 함).

4. Visual Studio 구독 관리 포털로 돌아갑니다. **여러 구독자 업로드** 대화 상자에서 **찾아보기**를 클릭합니다.
   > [!div class="mx-imgBorder"]
   > ![저장된 템플릿으로 이동하여 여러 구독자 업로드](media/bulk-add-browse-saved-template.png)

5. 저장한 Excel 파일로 이동한 다음, **확인**을 클릭합니다.
   > [!div class="mx-imgBorder"]
   > ![Excel 템플릿을 업로드하여 여러 구독자 업로드](media/bulk-upload-subscribers.png)

    업로드 진행률 대화 상자가 표시됩니다.

    템플릿에 오류가 있는 경우 업로드가 실패합니다. 그러면 템플릿을 수정하고 대량 업로드를 다시 시도할 수 있도록 오류 메시지가 표시됩니다.
   > [!div class="mx-imgBorder"]
   > ![여러 구독자 업로드에 실패한 경우 오류 메시지](media/bulk-add-template-failed.png)

    업로드가 성공적으로 완료되면 구독자 목록과 확인 메시지가 표시됩니다.
   > [!div class="mx-imgBorder"]
   > ![여러 구독자 업로드에 성공한 경우 확인 메시지](media/bulk-add-template-success.png)
