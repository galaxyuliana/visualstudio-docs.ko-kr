---
title: 스냅샷 디버깅 문제 해결 | Microsoft Docs
ms.custom: ''
ms.date: 04/24/2019
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3c66ba4a5031326ec288d3a5f2f3c4851d17ca6
ms.sourcegitcommit: 74c5360186731de07828764eb32ea1033a8c2275
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559749"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio의 스냅샷 디버깅에 대한 문제 해결 및 알려진 문제

이 문서에 설명 된 문제를 해결 되지 않으면에서 문제를 검색할 [개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/8/index.html) 를 선택 하 여 새 문제 보고 또는 **도움말** > **사용자 의견 보내기**   >  **문제 보고** Visual Studio에서.

## <a name="issue-attach-snapshot-debugger-encounters-an-http-status-code-error"></a>문제: HTTP 상태 코드 오류를 발견 하면 "스냅숏 디버거 연결"

다음 오류가 표시 되는 **출력** 연결 하려고 하는 동안 창 아래에 나열 된 알려진된 문제를 수 있습니다. 제안 된 솔루션을 시도 하 고 문제가 지속 되 별칭 앞에 문의 합니다.

`[TIMESTAMP] Error --- Unable to Start Snapshot Debugger - Attach Snapshot Debugger failed: System.Net.WebException: The remote server returned an error: (###) XXXXXX`

### <a name="401-unauthorized"></a>(401) Unauthorized

이 오류는 REST 호출에 발급 된 Visual Studio에서 Azure 사용 하 여 잘못 된 자격 증명을 나타냅니다. Azure Active Directory 쉽게 OAuth 모듈을 사용 하 여 알려진된 버그는이 오류를 생성할 수 있습니다.

다음 단계를 수행하세요.

* Visual Studio 개인 설정 계정을 Azure 구독 및 리소스에 연결 되는 권한이 있는지 확인 합니다. 이 결정 하는 빠른 방법을에서 대화 상자에서 리소스를 사용할 수 있는지를 확인 하는 것 **디버깅할** > **스냅숏 디버거 연결...**   >  **Azure 리소스** > **기존 항목 선택**, 또는 클라우드 탐색기에서.
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

### <a name="403-forbidden"></a>(403) 사용할 수 없음

이 오류는 사용 권한이 거부 됩니다 나타냅니다. 이 많은 다른 문제로 인해 발생할 수 있습니다.

다음 단계를 수행하세요.

* Visual Studio 계정을 유효한 Azure 구독이 있는 리소스에 대 한 역할 기반 Access Control (RBAC) 권한이 있는지 확인 합니다. App Service에 대 한 권한이 있는지를 확인 [쿼리](https://docs.microsoft.com/rest/api/appservice/appserviceplans/get) App Service 계획에 앱을 호스트 합니다.
* 클라이언트 컴퓨터의 타임 스탬프 올바르고 최신 상태를 확인 합니다. 15 분 이상 요청 타임 스탬프의 일반적으로 외부 타임 스탬프를 사용 하 여 서버에이 오류가 발생합니다.
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

### <a name="404-not-found"></a>(404) 찾을 수 없음

이 오류는 서버에서 웹 사이트를 찾을 수 없습니다 나타냅니다.

다음 단계를 수행하세요.

* 웹 사이트를 배포 하 고 App Service 리소스에 연결 하는 실행 했는지 확인 합니다.
* Https:// 사이트 한지 확인\<리소스\>. azurewebsites.net
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

### <a name="406-not-acceptable"></a>(406) 허용 되지 않음

이 오류는 서버 요청의 Accept 헤더에 설정 된 형식에 응답할 수 없는 것을 나타냅니다.

다음 단계를 수행하세요.

* Https:// 사이트 한지 확인\<리소스\>. azurewebsites.net
* 사이트에 새 인스턴스를 마이그레이션되지 않았음을 확인 합니다. 스냅숏 디버거를 일시적으로이 오류를 생성할 수 있는 특정 인스턴스로 라우팅 요청에 대 한 ARRAffinity의 개념을 사용 합니다.
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

### <a name="409-conflict"></a>(409) 충돌

이 오류는 현재 서버 상태 충돌할 요청을 나타냅니다.

사용자가 application Insights에 사용 하도록 설정 하는 app Service에 대해 스냅숏 디버거를 연결 하려고 할 때 발생 하는 알려진된 문제입니다. Application Insights에이 문제를 일으키는 AppSettings의 Visual Studio 보다 다른 대/소문자를 사용 하 여 설정 합니다.

::: moniker range=">= vs-2019"
Visual Studio 2019에이 문제를 해결 한 것입니다.
::: moniker-end

다음 단계를 수행하세요.

::: moniker range="vs-2017"

* Azure portal에서 AppSettings의 SnapshotDebugger (SNAPSHOTDEBUGGER_EXTENSION_VERSION) 및 InstrumentationEngine (INSTRUMENTATIONENGINE_EXTENSION_VERSION)에 대 한 대문자 되는지 확인 합니다. 그렇지 않은 경우 업데이트 설정을 수동으로 강제로 사이트 다시 시작 합니다.
::: moniker-end
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

### <a name="500-internal-server-error"></a>(500) 내부 서버 오류

이 오류는 사이트 되었거나 완전히 중지 서버 요청을 처리할 수 없습니다 되었음을 나타냅니다. 스냅숏 디버거 함수만 응용 프로그램을 실행 합니다. [Application Insights 스냅숏 디버거](https://docs.microsoft.com/azure/azure-monitor/app/snapshot-debugger) 예외에서 스냅숏을 제공 하 고 요구 사항에 가장 적합 한 도구를 사용할 수 있습니다.

### <a name="502-bad-gateway"></a>잘못 된 게이트웨이 (502)

이 오류는 서버 쪽 네트워킹 문제를 나타냅니다. 및 두 일 수 있습니다.

다음 단계를 수행하세요.

* 스냅숏 디버거를 다시 연결 하기 전에 잠시 대기를 시도 합니다.
* 이 오류가 계속 지속 되 면이 문서의 시작 부분에 설명 된 피드백 채널 중 하나를 사용 합니다.

## <a name="issue-snappoint-does-not-turn-on"></a>문제: Snappoint 본체가 켜지 지 않는다

snappoint와 함께 일반 snappoint 아이콘이 아닌 경고 아이콘(![snappoint 경고 아이콘](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "snappoint 경고 아이콘"))이 표시되면 snappoint가 켜지지 않은 것입니다.

![snappoint가 켜지지 않음](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "snappoint가 켜지지 않음")

다음 단계를 수행하세요.

1. 소스 코드를 빌드하고 앱을 배포할 때 사용한 동일한 버전이 있는지 확인 합니다. 사용자의 배포에 맞게 올바른 기호를 로드하는지 확인합니다. 이렇게 하려면 스냅샷 디버그 중에 **모듈** 창을 보고 디버그하는 모듈에 대해 로드된 .pdb 파일이 기호 파일 열에 표시되는지 확인합니다. 스냅샷 디버거는 자동으로 사용자의 배포에 맞게 기호를 다운로드하여 사용하려고 합니다.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>문제: 스냅숏을 열면 기호를 로드 하지 않습니다.

다음 창이 표시되면 기호가 로드되지 않은 것입니다.

![기호가 로드되지 않음](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "기호가 로드되지 않음")

다음 단계를 수행하세요.

- 이 페이지에서 **기호 설정 변경...** 링크를 클릭합니다. **디버깅 > 기호** 설정에서 기호 캐시 디렉터리를 추가합니다. 기호 경로가 설정되면 스냅샷 디버깅을 다시 시작합니다.

   프로젝트에서 사용할 수 있는 기호 또는 .pdb 파일은 App Service 배포와 일치해야 합니다. 대부분의 배포(Visual Studio를 통한 배포, Azure Pipelines 또는 Kudu를 통한 CI/CD 등)는 사용자의 App Service에 기호 파일을 게시합니다. 기호 캐시 디렉터리를 설정하면 Visual Studio에서 해당 기호를 사용할 수 있습니다.

   ![기호 설정](../debugger/media/snapshot-troubleshooting-symbol-settings.png "기호 설정")

- 조직이 기호 서버를 사용하거나 다른 경로에 기호를 드롭하는 경우 기호 설정을 사용하여 배포에 맞게 올바른 기호를 로드하세요.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>문제: 클라우드 탐색기에서 "스냅숏 디버거 연결" 옵션을 볼 수 없는

다음 단계를 수행하세요.

- 스냅샷 디버거 구성 요소가 설치되어 있는지 확인합니다. Visual Studio 설치 관리자를 열고 Azure 워크로드에서 **스냅샷 디버거** 구성 요소를 확인합니다.
::: moniker range="< vs-2019"
- 앱이 지원되는지 확인합니다. 현재 Azure App Services에 배포된 ASP.NET(4.6.1 이상) 및 ASP.NET Core(2.0 이상) 앱만 지원됩니다.
::: moniker-end
::: moniker range=">= vs-2019"
- 앱이 지원되는지 확인합니다.
  - Azure App Services - .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 애플리케이션
  - Azure App Services - Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 애플리케이션
  - Azure Virtual Machines(및 가상 머신 확장 집합) - .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 애플리케이션
  - Azure Virtual Machines(및 가상 머신 확장 집합) - Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 애플리케이션
  - Azure Kubernetes Service - Debian 9의 .NET Core 2.2 이상에서 실행되는 ASP.NET Core 애플리케이션
  - Azure Kubernetes Service - Alpine 3.8의 .NET Core 2.2 이상에서 실행되는 ASP.NET Core 애플리케이션
  - Azure Kubernetes Service - Ubuntu 18.04의 .NET Core 2.2 이상에서 실행되는 ASP.NET Core 애플리케이션
::: moniker-end

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>문제: 표시 되는 진단 도구에서 스냅숏 제한

![제한된 snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "제한된 snappoint")

다음 단계를 수행하세요.

- 스냅샷은 메모리를 거의 차지하지 않지만 할당된 메모리를 차지합니다. 스냅샷 디버거는 서버의 메모리가 과도하게 사용되는 것을 감지하면 스냅샷을 생성하지 않습니다. 스냅샷 디버거 세션을 중지하고 다시 시도하여 이미 캡처된 스냅샷을 삭제할 수 있습니다.

::: moniker range=">= vs-2019"
## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>문제: 오류에서는 여러 버전의 Visual Studio를 사용 하 여 스냅숏 디버깅

Visual Studio 2019에 최신 버전의 Azure App Service에서 스냅숏 디버거 사이트 확장에 필요합니다.  이 버전이 이전 버전의 Visual Studio 2017에서 사용 되는 스냅숏 디버거 사이트 확장을 사용 하 여 호환 되지 않습니다.  Visual Studio 2017의 스냅숏 디버거를 통해 이전에 디버깅에 Azure App Service에 Visual Studio 2019에 스냅숏 디버거를 연결 하려고 하면 다음 오류가 받습니다.

![호환 되지 않는 스냅숏 디버거 사이트 확장 Visual Studio 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "Visual Studio 2019 호환 되지 않는 스냅숏 디버거 사이트 확장")

반대로, Visual Studio 2019에 스냅숏 디버거를 통해 이전에 디버깅에 Azure App Service에 스냅숏 디버거를 연결 하려면 Visual Studio 2017을 사용 하는 경우 얻게 오류:

![호환 되지 않는 스냅숏 디버거 사이트 확장 Visual Studio 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "호환 되지 않는 스냅숏 디버거 사이트 확장 Visual Studio 2017")

이 문제를 해결하려면 Azure Portal에서 다음 앱 설정을 삭제하고 스냅샷 디버거를 다시 연결하세요.

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION
::: moniker-end

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>문제: 스냅숏 디버깅 때 문제가 및 자세한 로깅을 사용 하도록 설정 해야 하는 경우

### <a name="enable-agent-logs"></a>에이전트 로그 사용

에이전트 로깅을 사용하거나 사용하지 않도록 설정하려면 Visual Studio를 열고 ‘도구>옵션>스냅숏 디버거>에이전트 로깅 사용’으로 이동합니다. ‘세션을 시작할 때 오래된 에이전트 로그 삭제’도 사용하도록 설정되어 있는 경우 Visual Studio 연결이 성공할 때마다 이전 에이전트 로그가 삭제됩니다.

에이전트 로그는 다음 위치에 있습니다.

- App Services:
  - App Service의 Kudu 사이트(yourappservice.**scm**.azurewebsites.net)로 이동한 후 디버그 콘솔로 이동합니다.
  - 에이전트 로그는 다음 디렉터리에 저장 됩니다.  D:\home\LogFiles\SiteExtensions\DiagnosticsAgentLogs\
- VM/VMSS:
  - 로그는 다음과 같이 저장 됩니다 하는 에이전트 VM에 로그인 합니다.  C:\WindowsAzure\Logs\Plugins\Microsoft.Azure.Diagnostics.IaaSDiagnostics\<Version>\SnapshotDebuggerAgent_*.txt
- AKS
  - /tmp/diag/AgentLogs/* 디렉터리로 이동합니다.

### <a name="enable-profilerinstrumentation-logs"></a>프로파일러/계측 로그 사용

계측 로그는 다음 위치에 있습니다.

- App Services:
  - 오류 로깅 D:\Home\LogFiles\eventlog.xml 자동으로 전송 되, 이벤트로 표시 된 `<Provider Name="Instrumentation Engine" />` 또는 "프로덕션 중단점"
- VM/VMSS:
  - VM에 로그인하고 이벤트 뷰어를 엽니다.
  - 다음 보기를 엽니다. *Windows 로그 > 응용 프로그램*합니다.
  - ‘프로덕션 중단점’ 또는 ‘계측 엔진’을 사용하여 ‘이벤트 원본’별로 ‘현재 로그를 필터링’합니다.
- AKS
  - 계측 엔진 로깅은 /tmp/diag/log.txt(DockerFile의 MicrosoftInstrumentationEngine_FileLogPath 설정)에서 수행됩니다.
  - 프로덕션 중단점 로그는 /tmp/diag/shLog.txt에 있습니다.

## <a name="known-issues"></a>알려진 문제

- 동일한 App Service에 대해 여러 Visual Studio 클라이언트를 사용하는 스냅샷 디버깅은 현재 지원되지 않습니다.
- ASP.NET Core 프로젝트에서는 Roslyn IL 최적화가 일부만 지원됩니다. 일부 ASP.NET Core 프로젝트의 경우 일부 변수를 볼 수 없거나 조건문에 사용할 수 없습니다.
- *$FUNCTION* 또는 *$CALLER*와 같은 특수 변수는 ASP.NET Core 프로젝트의 조건문이나 logpoint에서 평가할 수 없습니다.
- 스냅샷 디버깅은 [로컬 캐싱](/azure/app-service/app-service-local-cache)이 켜져 있는 App Services에서 작동하지 않습니다.
- 스냅샷 디버깅 API Apps는 현재 지원되지 않습니다.

## <a name="site-extension-upgrade"></a>사이트 확장 업그레이드

스냅샷 디버깅 및 Application Insights에 영향을 미치는 ICorProfiler는 업그레이드하는 동안 사이트 프로세스에 로드되어 파일 잠금 문제를 일으킵니다. 프로덕션 사이트에 가동 중지 시간이 발생하지 않도록 다음 프로세스를 사용하는 것이 좋습니다.

- App Service 내에 [배포 슬롯](/azure/app-service/web-sites-staged-publishing)을 만들고 이 슬롯에 사이트를 배포합니다.
- 이 슬롯을 Visual Studio에 있는 클라우드 탐색기 또는 Azure Portal의 프로덕션과 교환합니다.
- 슬롯 사이트를 중지합니다. 모든 인스턴스의 사이트 w3wp.exe 프로세스를 종료하는 데는 몇 초가 걸립니다.
- Kudu 사이트 또는 Azure Portal(‘App Service 블레이드 > 개발 도구 > 확장 > 업데이트’)에서 슬롯 사이트 확장을 업그레이드합니다.
- 슬롯 사이트를 시작합니다. 사이트를 방문하여 다시 사이트를 준비하는 것이 좋습니다.
- 슬롯을 프로덕션과 교환합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 디버깅](../debugger/index.md)
- [스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)
- [라이브 ASP.NET Azure 가상 Machines\Virtual Machines Scale Sets 스냅숏 디버거를 사용 하 여 디버그](../debugger/debug-live-azure-virtual-machines.md)
- [스냅숏 디버거를 사용 하 여 라이브 ASP.NET Azure Kubernetes 디버깅](../debugger/debug-live-azure-kubernetes.md)
- [스냅샷 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)
