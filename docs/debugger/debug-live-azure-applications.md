---
title: 라이브 ASP.NET Azure 앱 디버그
description: Snappoint를 설정 하 고 스냅숏 디버거를 사용 하 여 스냅숏을 보는 방법에 알아봅니다.
ms.custom: mvc
ms.date: 03/16/2018
ms.topic: conceptual
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
- azure
ms.openlocfilehash: f0936078039c4c1071f0214b61702a7f57f794ec
ms.sourcegitcommit: 0f7411c1a47d996907a028e920b73b53c2098c9f
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690194"
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>스냅숏 디버거를 사용 하 여 라이브 ASP.NET Azure 앱 디버그

스냅숏 디버거는 관심이 있는 코드가 실행 되 면 프로덕션 앱의 스냅숏을 만듭니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 애플리케이션의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

Snappoint 및 logpoint 중단점, 유사 하지만 중단점과 달리 snappoint 응용 프로그램을 중지 하지 적중 될 때입니다. 일반적으로 snappoint에 스냅숏을 캡처하는 10 ~ 20 밀리초입니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 스냅숏 디버거를 시작 합니다.
> * Snappoint를 설정 하 고 스냅숏 보기
> * Logpoint를 설정 합니다.

## <a name="prerequisites"></a>전제 조건

* 스냅숏 디버거는 Visual Studio 2017 Enterprise 버전 15.5 이상을 사용할 수는 **Azure 개발 워크 로드**합니다. (아래 합니다 **개별 구성 요소** 를 탭 하면 아래에서 찾을 **디버깅 및 테스트** > **스냅숏 디버거**.)

    설치 되어 있지 않은 경우 설치할 [Visual Studio 2017 Enterprise 버전 15.5](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) 이상. 이전 Visual Studio 2017 설치에서를 업데이트 하는 경우 Visual Studio 설치 관리자를 실행 하 고 스냅숏 디버거 구성 요소를 확인 합니다 **ASP.NET 및 웹 개발 워크 로드**합니다.

* 기본 또는 그 이상의 Azure App Service 계획입니다.

* 스냅숏 컬렉션은 Azure App Service에서 실행되는 다음 웹앱에서 사용할 수 있습니다.

    * .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 애플리케이션
    * Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 애플리케이션

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>프로젝트를 열고 스냅숏 디버거를 시작 합니다.

1. 스냅숏 디버그 하려는 프로젝트를 엽니다.

    > [!IMPORTANT]
    > 스냅숏 디버그 하려면 엽니다는 **동일한 버전의 소스 코드** Azure App Service에 게시 된 합니다.

1. 클라우드 탐색기에서 (**보기 > 클라우드 탐색기**), Azure App Service에 배포 된 프로젝트를 마우스 오른쪽 단추로 **스냅숏 디버거 연결**합니다.

   ![스냅숏 디버거를 시작 합니다.](../debugger/media/snapshot-launch.png)

    처음으로 선택 하면 **스냅숏 디버거 연결**, Azure App Service에서 스냅숏 디버거 사이트 확장을 설치 하 라는 메시지가 나타납니다. 이 설치에는 Azure App Service를 다시 시작을 해야 합니다.

   Visual Studio 스냅숏 디버깅 모드에에서 포함 되었습니다.

    > [!NOTE]
    > Application Insights 사이트 확장은 또한 스냅숏 디버깅을 지원합니다. "사이트 확장 만료" 오류 메시지에서 발견 되 면 참조 [문제 해결 팁 및 스냅숏 디버깅에 대 한 알려진된 문제](../debugger/debug-live-azure-apps-troubleshooting.md) 세부 정보를 업그레이드 합니다.

   ![스냅숏 디버깅 모드](../debugger/media/snapshot-message.png)

   합니다 **모듈** 창에 표시 된 모듈을 모두 Azure App Service에 대 한 로드 한 경우 (선택 **디버그 / Windows / 모듈** 이 창을 열려면).

   ![모듈 창을 확인 합니다.](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Snappoint를 설정 합니다.

1. 코드 편집기에서 관심 snappoint를 설정 하려면 코드 줄 옆에 있는 왼쪽된 여백을 클릭 합니다. 실행될지 알고 있는 코드 인지 확인 합니다.

   ![Snappoint를 설정 합니다.](../debugger/media/snapshot-set-snappoint.png)

2. 클릭 **수집 시작** snappoint를 설정 하려면.

   ![설정 된 snappoint](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 스냅숏을 볼 때 실행할 수 없습니다 하지만 서로 다른 코드 줄에서 실행을 수행 하려면 코드에서 여러 snappoint를 배치할 수 있습니다. 코드에서 snappoint 여러 개 있는 경우 스냅숏 디버거 하면 해당 스냅숏을 같은 최종 사용자 세션의 지 합니다. 스냅숏 디버거는 여러 사용자가 앱에 도달 하는 경우에 합니다.

## <a name="take-a-snapshot"></a>스냅숏 가져오기

Snappoint를 켤 때에 snappoint를 배치할 코드 줄이 실행 될 때마다 스냅숏을 캡처하려면 됩니다. 이 실행은 서버의 실제 요청에 의해 발생할 수 있습니다. 방문, 보기로 이동 하 여 브라우저에 웹 사이트의 모든 작업을 수행 하 여 snappoint를 강제로 적중 될 프로그램 snappoint를 발생 시키는 데 필요 합니다.

## <a name="inspect-snapshot-data"></a>스냅숏 데이터를 검사 합니다.

1. Snappoint는 적중 될 때 스냅숏이 진단 도구 창에 표시 됩니다. 선택이 창을 열려면 **디버그 / Windows / 진단 도구 표시**합니다.

   ![Snappoint를 열려면](../debugger/media/snapshot-diagsession-window.png)

1. 코드 편집기에서 스냅숏을 열기 위한 snappoint를 두 번 클릭 합니다.

   ![스냅숏 데이터를 검사 합니다.](../debugger/media/snapshot-inspect-data.png)

   DataTips 보기를 사용 하 여 변수를 마우스로 가리키면이 뷰에서 **지역**, **조사식**, 및 **호출 스택** windows 식을 평가 합니다.

    라이브 상태인 웹 사이트 자체 이며 최종 사용자에 게 영향을 받는 되지 않습니다. 기본적으로 하나의 스냅숏을 캡처하도록 snappoint 당:는 snappoint 해제 스냅숏으로 캡처된 후 합니다. snappoint에 다른 스냅숏을 캡처하려면 하려는 경우 켤 수 있습니다 snappoint를 다시 클릭 하 여 **컬렉션 업데이트**합니다.

또한 자세한 snappoint를 앱에 추가 하 고 사용 하 여 켜도록 수는 **컬렉션 업데이트** 단추입니다.

**도움이 필요하세요?** 참조 된 [문제 해결 및 알려진된 문제](../debugger/debug-live-azure-apps-troubleshooting.md) 하 고 [스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md) 페이지.

## <a name="set-a-conditional-snappoint"></a>조건부 snappoint를 설정 합니다.

앱에서 특정 상태를 다시 하기 어려운 경우에 조건부 snappoint 사용을 위해 하는 것이 좋습니다. 조건부 snappoint 도움말 앱 변수 검사 하려는 특정 값에 하는 경우와 같이 원하는 상태가 될 때까지 스냅숏을 만드는 것을 방지 합니다. 필터 식을 사용 하는 조건을 설정할 수도 있고 적중 횟수 수 있습니다.

#### <a name="to-create-a-conditional-snappoint"></a>조건부 snappoint를 만들려면

1. Snappoint 아이콘 (속이 빈 공)를 마우스 오른쪽 단추로 클릭 하 고 선택 **설정을**합니다.

   ![설정 선택](../debugger/media/snapshot-snappoint-settings.png)

1. Snappoint 설정 창에서 식을 입력 합니다.

   ![식을 입력 합니다.](../debugger/media/snapshot-snappoint-conditions.png)

   앞의 그림에만 스냅숏이 만들어질는 snappoint에 대해 때 `visitor.FirstName == "Dan"`합니다.

## <a name="set-a-logpoint"></a>Logpoint를 설정 합니다.

Snappoint가 적중할 때 스냅숏 만들기, 하는 것 외에도 구성할 수도 있습니다는 메시지를 기록할 snappoint (즉, 한 logpoint 만들기). 앱을 다시 배포 하지 않고도 logpoint를 설정할 수 있습니다. Logpoint 거의 실행 되 고 그 영향이 없거나 실행 중인 응용 프로그램에 파생 작업이 발생 합니다.

#### <a name="to-create-a-logpoint"></a>Logpoint를 만들려면

1. Snappoint 아이콘 (파란색 육각형)를 마우스 오른쪽 단추로 클릭 하 고 선택 **설정을**합니다.

1. Snappoint 설정 창에서 선택 **작업**합니다.

    ![만들기는 logpoint](../debugger/media/snapshot-logpoint.png)

1. 메시지 필드에 기록 하려는 새 로그 메시지를 입력할 수 있습니다. 중괄호 안에 배치 하 여 로그 메시지의 변수를 평가할 수 있습니다.

    선택 하면 **출력 창에 보냅니다**는 logpoint에 도달 하면 진단 도구 창에서 메시지가 표시 됩니다.

    ![Logpoint diagsession 창에는 데이터](../debugger/media/snapshot-logpoint-output.png)

    선택 하면 **응용 프로그램 로그 보내기**는 logpoint 적중 될 때, 메시지의 메시지에서 볼 수 있는 아무 곳 이나 표시 `System.Diagnostics.Trace` (또는 `ILogger` .NET Core에서)와 같은 [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 스냅숏 디버거를 사용 하는 방법을 알아보았습니다. 이 기능에 대 한 자세한 정보를 보려면 좋습니다.

> [!div class="nextstepaction"]
> [스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)
