---
title: 스냅숏 디버깅 문제 해결 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/07/2017
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 817e6f31d9282caf77c9f403c7e5555075726d2d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54943801"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio에서 스냅숏 디버깅 문제 해결 및 알려진 문제

이 문서에 설명 된 문제를 해결 되지 않으면, 문의 snaphelp@microsoft.com합니다.

## <a name="issue-snappoint-does-not-turn-on"></a>문제: Snappoint 본체가 켜지 지 않는다

경고 아이콘이 표시 되 면 ![Snappoint 경고 아이콘이](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "Snappoint 경고 아이콘이") 일반 snappoint 아이콘 대신 프로그램 snappoint를 사용 하 여 다음을 snappoint 켜져 있지 않습니다.

![Snappoint 본체가 켜지 지 않는다](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint 본체가 켜지 지 않는다")

다음이 단계를 수행 합니다.

1. 빌드 및 배포에 app.isua1 하는 데 사용 된 소스 코드의 같은 버전이 있는지 확인 합니다. 배포에 대 한 올바른 기호를 로드 하는 있는지 확인 합니다. 이렇게 하려면 보기를 **모듈** 창 스냅숏 디버깅 하는 동안 및 기호 파일 열에는 표시.pdb 파일을 디버깅 하는 모듈에 대 한 로드를 확인 합니다. 스냅숏 디버거는 자동으로 다운로드 하 고 배포에 대 한 기호를 사용 하려고 합니다.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>문제: 스냅숏을 열면 기호를 로드 하지 않습니다.

다음 창 표시 되 면 기호가 로드 되지 않았습니다.

![기호를 로드 하지 않습니다](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "기호를 로드 하지 않습니다")

다음이 단계를 수행 합니다.

- 클릭 된 **기호 설정을 변경 하는 중...** 이 페이지에 연결 합니다. 에 **디버깅 > 기호** 설정, 기호 캐시 디렉터리를 추가 합니다. 스냅숏 디버깅 기호 경로 설정한 후 다시 시작 합니다.

   기호 또는.pdb 파일을 프로젝트에서 사용할 수 있는 App Service 배포를 일치 해야 합니다. 대부분의 배포 (Visual Studio, Azure 파이프라인 또는 Kudu를 사용한 CI/CD를 통해 배포 등) App Service에 따라 기호 파일을 게시 합니다. 이러한 기호를 사용 하려면 Visual Studio를 사용 하면 기호 캐시 디렉터리를 설정 합니다.

   ![기호 설정](../debugger/media/snapshot-troubleshooting-symbol-settings.png "기호 설정")

- 또는 조직 기호 서버를 사용 하 여 또는 다른 경로에서 기호를 삭제 하는 경우 배포에 대 한 올바른 기호를 로드 하려면 기호 설정을 사용 합니다.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>문제: 클라우드 탐색기에서 "스냅숏 디버거 연결" 옵션을 볼 수 없는

다음이 단계를 수행 합니다.

- 스냅숏 디버거 구성 요소가 설치 되어 있는지 확인 합니다. Visual Studio 설치 관리자를 열고 확인 합니다 **스냅숏 디버거** Azure 워크 로드 구성 요소입니다.
- 앱 지원 되는지 확인 합니다. 현재만 ASP.NET (4.6.1+) 및 Azure App Services에 배포 된 ASP.NET Core (2.0 이상) 앱 지원 됩니다.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>문제: 표시 되는 진단 도구에서 스냅숏 제한

![제한 됨 snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "snappoint를 제한 합니다.")

다음이 단계를 수행 합니다.

- 스냅숏은 작은 메모리를 차지 하지만 커밋 요금이 부과 됩니다. 스냅숏 디버거는 서버에 과도 한 메모리 부하가 감지 하는 경우 스냅숏은 적용 되지 않습니다. 스냅숏 디버거 세션을 중지 하 고 다시 시도 하 여 이미 캡처된 스냅숏을 삭제할 수 있습니다.

## <a name="known-issues"></a>알려진 문제

- 동일한 App Service에 대 한 여러 Visual Studio 클라이언트를 사용 하 여 스냅숏 디버깅 현재 지원 되지 않습니다.
- Roslyn IL 최적화 ASP.NET Core 프로젝트에서 완전히 지원 되지 않습니다. 일부 ASP.NET Core 프로젝트에 대 한 몇 가지 변수를 참조 하세요. 또는 조건문에서 일부 변수를 사용 하 여 못할 수 있습니다. 
- 특수 변수와 같은 *$FUNCTION* 하거나 *$CALLER*, 조건문 또는 ASP.NET Core 프로젝트에 대 한 logpoint 계산할 수 없습니다.
- 스냅숏 디버깅 있는 App Services에서 작동 하지 않습니다 [로컬 캐싱](/azure/app-service/app-service-local-cache) 켜져 있습니다.
- API 앱을 디버깅 하는 스냅숏 현재 지원 되지 않습니다.

## <a name="site-extension-upgrade"></a>사이트 확장 업그레이드

스냅숏 디버깅 및 Application Insights 사이트 프로세스로 로드 하 고 업그레이드 하는 동안 파일 잠금 문제가 발생 하는 ICorProfiler에 따라 달라 집니다. 프로덕션 사이트에 없는 중단 시간이 보장 하기 위해이 프로세스를 사용 하는 것이 좋습니다.

- 만들기는 [배포 슬롯](/azure/app-service/web-sites-staged-publishing) App Service 내에서 사이트 슬롯에 배포 합니다.
- Visual Studio에서 클라우드 탐색기 또는 Azure portal에서 사용 하 여 프로덕션 슬롯을 교환 합니다.
- 슬롯 사이트를 중지 합니다. 이 모든 인스턴스에서 사이트 w3wp.exe 프로세스를 중지 하는 데 몇 초가 걸립니다.
- Kudu 사이트 또는 Azure portal에서 슬롯 사이트 확장을 업그레이드 (*App Service 블레이드 > 개발 도구 > 확장 > 업데이트*).
- 슬롯 사이트를 시작 합니다. 다시 준비 사이트를 방문 하는 것이 좋습니다.
- 프로덕션 슬롯을 교환 합니다.

## <a name="see-also"></a>참고 항목

[Visual Studio의 디버깅](../debugger/index.md)  
[스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)  
[스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)  
