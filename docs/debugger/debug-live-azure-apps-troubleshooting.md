---
title: 스냅숏 디버깅 문제 해결 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/07/2018
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b7916cbd3a7faa633baf53a18686779dc2b386c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857764"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio의 스냅숏 디버깅에 대한 문제 해결 및 알려진 문제

이 문서에 설명된 단계를 수행해도 문제가 해결되지 않으면 snaphelp@microsoft.com에 문의하세요.

## <a name="issue-snappoint-does-not-turn-on"></a>문제: Snappoint 본체가 켜지 지 않는다

snappoint와 함께 일반 snappoint 아이콘이 아닌 경고 아이콘(![snappoint 경고 아이콘](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "snappoint 경고 아이콘"))이 표시되면 snappoint가 켜지지 않은 것입니다.

![snappoint가 켜지지 않음](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "snappoint가 켜지지 않음")

다음 단계를 수행하세요.

1. app.isua1을 빌드하고 배포하는 데 사용된 것과 동일한 버전의 소스 코드가 있는지 확인합니다. 사용자의 배포에 맞게 올바른 기호를 로드하는지 확인합니다. 이렇게 하려면 스냅숏 디버그 중에 **모듈** 창을 보고 디버그하는 모듈에 대해 로드된 .pdb 파일이 기호 파일 열에 표시되는지 확인합니다. 스냅숏 디버거는 자동으로 사용자의 배포에 맞게 기호를 다운로드하여 사용하려고 합니다.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>문제: 스냅숏을 열면 기호를 로드 하지 않습니다.

다음 창이 표시되면 기호가 로드되지 않은 것입니다.

![기호가 로드되지 않음](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "기호가 로드되지 않음")

다음 단계를 수행하세요.

- 이 페이지에서 **기호 설정 변경...** 링크를 클릭합니다. **디버깅 > 기호** 설정에서 기호 캐시 디렉터리를 추가합니다. 기호 경로가 설정되면 스냅숏 디버깅을 다시 시작합니다.

   프로젝트에서 사용할 수 있는 기호 또는 .pdb 파일은 App Service 배포와 일치해야 합니다. 대부분의 배포(Visual Studio를 통한 배포, Azure Pipelines 또는 Kudu를 통한 CI/CD 등)는 사용자의 App Service에 기호 파일을 게시합니다. 기호 캐시 디렉터리를 설정하면 Visual Studio에서 해당 기호를 사용할 수 있습니다.

   ![기호 설정](../debugger/media/snapshot-troubleshooting-symbol-settings.png "기호 설정")

- 조직이 기호 서버를 사용하거나 다른 경로에 기호를 드롭하는 경우 기호 설정을 사용하여 배포에 맞게 올바른 기호를 로드하세요.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>문제: 클라우드 탐색기에서 "스냅숏 디버거 연결" 옵션을 볼 수 없는

다음 단계를 수행하세요.

- 스냅숏 디버거 구성 요소가 설치되어 있는지 확인합니다. Visual Studio 설치 관리자를 열고 Azure 워크로드에서 **스냅숏 디버거** 구성 요소를 확인합니다.
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

- 스냅숏은 메모리를 거의 차지하지 않지만 할당된 메모리를 차지합니다. 스냅숏 디버거는 서버의 메모리가 과도하게 사용되는 것을 감지하면 스냅숏을 생성하지 않습니다. 스냅숏 디버거 세션을 중지하고 다시 시도하여 이미 캡처된 스냅숏을 삭제할 수 있습니다.

## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>문제: 오류에서는 여러 버전의 Visual Studio를 사용 하 여 스냅숏 디버깅

VS 2019를 사용하려면 Azure App Service에 최신 버전의 스냅숏 디버거 사이트 확장이 있어야 합니다.  이 버전은 VS 2017에서 사용하는 이전 버전의 스냅숏 디버거 사이트 확장과 호환되지 않습니다.  이전에 VS 2017의 스냅숏 디버거가 디버그했던 Azure App Service에 VS 2019의 스냅숏 디버거를 연결하려고 하면 다음 오류가 발생합니다.

![호환되지 않는 스냅숏 디버거 사이트 확장 VS 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "호환되지 않는 스냅숏 디버거 사이트 확장 VS 2019")

반대로 이전에 VS 2019의 스냅숏 디버거가 디버그했던 Azure App Service에 VS 2017을 사용하여 스냅숏 디버거를 연결하면 다음 오류가 발생합니다.

![호환되지 않는 스냅숏 디버거 사이트 확장 VS 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "호환되지 않는 스냅숏 디버거 사이트 확장 VS2017")

이 문제를 해결하려면 Azure Portal에서 다음 앱 설정을 삭제하고 스냅숏 디버거를 다시 연결하세요.

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION

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
  - 오류 로깅은 자동으로 D:\Home\LogFiles\eventlog.xml로 전송되며, 이벤트는 <<공급자 이름=“계측 엔진” //>> 또는 “프로덕션 중단점”으로 표시됩니다.
- VM/VMSS:
  - VM에 로그인하고 이벤트 뷰어를 엽니다.
  - 다음 보기를 엽니다. *Windows 로그 > 응용 프로그램*합니다.
  - ‘프로덕션 중단점’ 또는 ‘계측 엔진’을 사용하여 ‘이벤트 원본’별로 ‘현재 로그를 필터링’합니다.
- AKS
  - 계측 엔진 로깅은 /tmp/diag/log.txt(DockerFile의 MicrosoftInstrumentationEngine_FileLogPath 설정)에서 수행됩니다.
  - 프로덕션 중단점 로그는 /tmp/diag/shLog.txt에 있습니다.

## <a name="known-issues"></a>알려진 문제

- 동일한 App Service에 대해 여러 Visual Studio 클라이언트를 사용하는 스냅숏 디버깅은 현재 지원되지 않습니다.
- ASP.NET Core 프로젝트에서는 Roslyn IL 최적화가 일부만 지원됩니다. 일부 ASP.NET Core 프로젝트의 경우 일부 변수를 볼 수 없거나 조건문에 사용할 수 없습니다.
- *$FUNCTION* 또는 *$CALLER*와 같은 특수 변수는 ASP.NET Core 프로젝트의 조건문이나 logpoint에서 평가할 수 없습니다.
- 스냅숏 디버깅은 [로컬 캐싱](/azure/app-service/app-service-local-cache)이 켜져 있는 App Services에서 작동하지 않습니다.
- 스냅숏 디버깅 API Apps는 현재 지원되지 않습니다.

## <a name="site-extension-upgrade"></a>사이트 확장 업그레이드

스냅숏 디버깅 및 Application Insights에 영향을 미치는 ICorProfiler는 업그레이드하는 동안 사이트 프로세스에 로드되어 파일 잠금 문제를 일으킵니다. 프로덕션 사이트에 가동 중지 시간이 발생하지 않도록 다음 프로세스를 사용하는 것이 좋습니다.

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
- [스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)