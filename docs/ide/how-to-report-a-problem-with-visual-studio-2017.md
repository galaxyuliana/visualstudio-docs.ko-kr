---
title: Visual Studio에서 문제를 보고하는 방법
titleSuffix: ''
description: Visual Studio 2017의 문제를 진단하고 수정할 수 있도록 Microsoft에 보고하는 방법을 알아봅니다.
ms.date: 03/11/2018
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4e9ce21c0abf365606b1c09aa37c59e4217feb02
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936930"
---
# <a name="how-to-report-a-problem-with-visual-studio-2017"></a>Visual Studio 2017의 문제를 보고하는 방법

Visual Studio에 문제가 발생하는 경우와 관련하여 자세히 알려고 합니다. 진단하고 해결할 수 있도록 [개발자 커뮤니티](https://developercommunity.visualstudio.com/)에 대한 문제를 보고하는 방법은 다음과 같습니다.

> [!NOTE]
> 이 토픽은 Windows의 Visual Studio에 적용됩니다. Mac용 Visual Studio는 [Mac용 Visual Studio에서 문제를 보고하는 방법](/visualstudio/mac/report-a-problem)을 참조하세요.

## <a name="report-a-problem-by-using-visual-studio"></a>Visual Studio를 사용하여 문제 보고

Visual Studio에 대한 문제를 보고하려면 Visual Studio 또는 Visual Studio 설치 관리자에서 보고서를 시작해야 합니다. [개발자 커뮤니티](https://developercommunity.visualstudio.com/) 웹 사이트를 통해 직접 수행할 수 없습니다. Visual Studio를 통해 보고하면 진단 정보를 보고서에 자동으로 포함할 수 있습니다.

![Visual Studio 개발자 커뮤니티에 대한 문제 팝업 보고](media/report-an-issue.png)

1. Visual Studio에서 **도움말** > **피드백 보내기** > **문제 보고**를 선택합니다.

   > [!TIP]
   > Visual Studio 설치를 완료할 수 없거나 Visual Studio 내에서 피드백 도구에 액세스할 수 없는 경우 **Visual Studio 설치 관리자**를 사용하여 문제를 보고할 수 있습니다. 이렇게 하려면 **Visual Studio 설치 관리자**의 오른쪽 위에서 피드백 아이콘을 선택합니다.

1. 로그인되지 않은 경우 다음 스크린샷과 같이 도구 오른쪽에 있는 **로그인**을 선택합니다. 화면의 지침에 따라 로그인합니다.

   ![로그인하여 문제 보고](../ide/media/sign-in-new-ux.png)

   로그인할 때 발생하는 문제를 보고할 수 있습니다. 게시한 다른 문제에 대해 투표하거나 주석으로 처리할 수도 있습니다.

1. 로그인하면 **팔로우한 항목** 화면에서 **문제** 및 **작업**을 확인할 수 있습니다.

    ![팔로우한 항목](../ide/media/items-i-follow.png)

1. Visual Studio는 문제를 검색하고 다른 사용자가 보고했는지를 확인하는 인터페이스를 제공합니다. 다른 사용자가 이미 보고한 경우 "투표"하여 알려 주시기 바랍니다.
   > [!NOTE]
   > 검색하기 위해 검색 상자에 원하는 텍스트를 입력하고 Enter 키를 클릭하거나 검색 아이콘을 누릅니다.

   ![유사한 문제 검색 및 투표](../ide/media/search-and-vote.png)

1. 발생한 문제를 찾을 수 없는 경우 화면 맨 아래에서 **새 문제 보고**를 선택합니다.

   > [!NOTE]
   > **새 문제 보고** 단추는 개발자 커뮤니티에 대한 Visual Studio 인터페이스에만 표시됩니다. [개발자 커뮤니티](https://developercommunity.visualstudio.com/) 웹 사이트에서 직접 문제를 보고할 수 없습니다.

1. 올바른 Visual Studio 팀에게 전달될 수 있도록 문제에 대한 설명이 포함된 제목을 입력합니다.

1. 추가 세부 정보와 문제를 재현을 위한 단계(가능한 경우)를 제공합니다.

   ![새 문제 보고](../ide/media/report-new-problem.png)

1. **다음**을 선택하여 **첨부 파일** 탭으로 이동합니다. 여기에서 현재 화면을 캡처하여 Microsoft로 보낼 수 있습니다. 추가 스크린샷 또는 다른 파일을 첨부하려면 **추가 파일 첨부**를 선택합니다.

   ![Visual Studio 문제 보고서에 스크린샷 첨부](media/report-a-problem-screenshot.png)

1. 스크린샷을 첨부하지 않거나 [재현을 기록](#record-a-repro)하지 않으려는 경우 **다음**을 선택하여 **요약** 탭으로 이동합니다.

1. **제출**을 선택하여 이미지 및 추적 또는 덤프 파일과 함께 보고서를 보냅니다. **제출** 단추가 회색으로 표시되는 경우 보고서의 제목과 설명을 입력했는지 확인합니다.

   수집되는 데이터에 대한 자세한 내용은 [수집한 데이터](developer-community-privacy.md#data-we-collect)를 참조하세요.

## <a name="record-a-repro"></a>재현 기록

추적 및 힙 덤프 파일은 문제를 진단하는 데 유용합니다. **문제 보고** 도구를 사용하여 재현 단계를 기록하여 데이터를 Microsoft로 보내 주시면 감사하겠습니다. 방법은 다음과 같습니다.

1. 문제에 대한 제목과 설명을 입력한 후에 **다음**을 선택하여 **첨부 파일** 탭으로 이동합니다.

1. **레코드** 탭을 선택합니다.

1. 문제를 재현할 수 있는 경우 **작업 기록**에서 Visual Studio의 현재 인스턴스를 선택합니다. 예를 들어 Visual Studio가 정지되어 수행할 수 없는 경우  **\<새 인스턴스 만들기>** 를 선택하여 Visual Studio의 새 인스턴스에서 작업을 기록합니다.

1. **기록 시작**을 선택합니다. 도구를 실행할 수 있는 권한을 제공합니다.

   ![Visual Studio 문제 보고에서 추적 및 힙 덤프 파일을 제공하도록 "기록 시작" 선택](../ide/media/record-dialog-box.png)

1. **단계 레코더** 도구가 나타나면 문제를 재현하는 단계를 수행합니다.

1. 작업이 완료되면 **기록 중지** 단추를 선택합니다.

1. Visual Studio에서 기록된 정보를 수집하여 패키징하는 동안 몇 분 정도 기다립니다.

   수집되는 데이터에 대한 자세한 내용은 [수집한 데이터](developer-community-privacy.md#data-we-collect)를 참조하세요.

## <a name="when-further-information-is-needed-need-more-info"></a>추가 정보가 필요한 경우(추가 정보 필요)

Visual Studio 2017 버전 15.5 부터는 사용자가 문제 보고에 대한 추가 정보를 제공할 수 있는 새 워크플로가 있습니다.

1. Microsoft 엔지니어가 [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/) 문제를 **추가 정보 필요** 상태로 설정하는 경우 문제에 대해 게시하거나, 투표하거나, 주석을 처리한 사용자는 Visual Studio의 **문제 보고** 도구에서 알림을 받습니다.

   ![Visual Studio의 추가 정보 필요 알림](../ide/media/nmi-notification.png)

1. **문제 보기** 링크를 클릭하여 주의가 필요한 문제에 대한 보기를 필터링하고 정렬합니다. 이러한 문제에는 옆에 지표가 있어서 일반적인 검색에서 구분합니다.

1. 문제를 클릭하여 문제 세부 정보 보기를 봅니다.

   ![추가 정보 필요 알림](../ide/media/nmi-details-view.png)

1. **추가 정보 필요** 요청을 보려면 문제 세부 정보 보기에서 **해당 요청 및 응답 보기** 링크를 클릭합니다. 대화 상자에는 다음 요청이 표시됩니다.

   ![추가 정보 필요 알림](../ide/media/nmi-request.png)

1. 주석, 첨부 파일 또는 기록 단계를 추가하여 자세한 정보를 제공할 수 있습니다. 이 환경은 문제에 투표하는 경우 새 문제 보고하거나 추가 정보를 제공하는 작업과 비슷합니다.

1. 요청한 Microsoft 엔지니어는 제공된 추가 정보에 대한 알림을 받습니다. 조사하는 데 충분한 정보가 있으면 문제 상태를 변경합니다. 그렇지 않으면 엔지니어도 추가 정보를 요청합니다.

   > [!NOTE]
   > * 회신하면 알림이 사라집니다. 해당 위치에는 감사의 말씀을 전하고 더 많은 정보를 제공하는 방법을 용이하게 하는 배너가 표시됩니다.
   > * 문제가 상태를 변경하면 문제를 팔로우하는 모든 사용자에 대한 알림이 사라집니다.
   > * 두 명 이상이 동일한 **추가 정보 필요** 요청에서 회신할 수 있습니다.
   > * 웹 브라우저를 통해 직접 액세스할 수 있는 경우 [개발자 커뮤니티](https://developercommunity.visualstudio.com/)에 **추가 정보 필요** 워크플로가 없지만 거기에서 주석 및 첨부 파일을 제공할 수도 있습니다.

## <a name="search-for-solutions-or-provide-feedback"></a>솔루션 검색 또는 피드백 제공

문제를 보고하기 위해 Visual Studio를 사용할 수 없거나 원하지 않는 경우 [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/) 페이지에 문제가 이미 보고되고 솔루션이 게시됐을 수 있습니다.

보고할 문제가 없지만 기능을 제안하려는 경우 따로 위치가 정해져 있습니다. 자세한 내용은 [기능 제안](https://developercommunity.visualstudio.com/content/idea/post.html?space=8) 페이지를 참조하세요.

## <a name="see-also"></a>참고 항목

* [의견 보내기](../ide/talk-to-us.md)
* [Mac용 Visual Studio의 문제 보고](/visualstudio/mac/report-a-problem)
* [C++를 사용하여 문제 보고](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)
* [개발자 커뮤니티 데이터 개인 정보](developer-community-privacy.md)