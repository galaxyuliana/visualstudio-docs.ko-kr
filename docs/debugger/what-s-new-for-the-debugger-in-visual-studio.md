---
title: Visual Studio 2017 디버거의 새로운 기능 | Microsoft Docs
titleSuffix: ''
ms.date: 01/22/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: 9c6f2eb4be56be8cf5e25c3238a91819df3bc574
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62901396"
---
# <a name="whats-new-for-the-debugger-in-visual-studio-2017"></a>Visual Studio 2017 디버거의 새로운 기능

디버거가 이러한 새 기능이 포함 되어 있습니다.

- 버전 15.5의에서 새로운 기능을 **스냅숏 디버거** 에 관심이 있는 코드가 실행 되 면 프로덕션 앱의 스냅숏을 만듭니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 애플리케이션의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

    스냅숏 컬렉션은 Azure App Service에서 실행되는 다음 웹앱에서 사용할 수 있습니다.

  * .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 애플리케이션
  * Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 애플리케이션

    자세한 내용은 [스냅숏 디버거를 사용하여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)를 참조하세요.

- 버전 15.5에서 Visual Studio Enterprise에만 새 **IntelliTrace 뒤로** 단계 이벤트에서 모든 중단점 및 디버거 응용 프로그램의 스냅숏을 자동으로 수행 합니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 애플리케이션의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 애플리케이션 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

    디버그 도구 모음의 **뒤로 가기**와 **앞으로 가기** 단추를 사용하여 이동하고 스냅숏을 볼 수 있습니다. 이 단추를 사용하여 **진단 도구** 창의 **이벤트** 탭에 나타나는 이벤트를 탐색할 수 있습니다.

    ![뒤로 가기 및 앞으로 가기 단추](../debugger/media/intellitrace-step-back-icons-description.png  "뒤로 가기 및 앞으로 가기 단추")

    자세한 내용은 [IntelliTrace를 사용하여 이전 앱 상태 검사](../debugger/view-historical-application-state.md) 페이지를 참조하세요.

- 합니다 **예외 도우미** 예외 도우미를 대체 하 고 오류가 발생 하는 비 모달 대화 상자에 표시 됩니다. 합니다 **예외 도우미** 모든 내부 예외, 디버거에서 (있는 경우), 추가 분석에 대 한 빠른 액세스 및 직접 액세스를 제공 합니다 **예외 설정** 예외에 대 한 합니다. 확인 해야 하는 것을 차단 하는 경우 예외 도우미 부동 보기로 끌 수도 있습니다.

    예를 들어, 한 **NullReferenceException** 이제 변수는 null 참조 (추가 정보)를 표시 합니다.

    ![디버거의 예외 도우미](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    자세한 내용은 [Using the New Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/)(Visual Studio에서 새 예외 도우미 사용) 블로그 게시물을 참조하세요.

- 이제 선택 하 여 디버거에서 일시 중지 된 동안 코드 줄을 실행할 수 있습니다 합니다 **여기까지 실행** 녹색 화살표 아이콘 (아이콘이 표시 코드 줄을 가리킬 때). 이렇게 하면 임시 중단점을 설정할 필요가 없습니다.

    ![디버거의 실행 하려면 클릭](../debugger/media/dbg-run-to-click.png "DbgRunToClick")

- 예외에 조건을 설정할 수 있습니다는 **예외 설정** 대화 상자 (사용 하 여이 수행할 수 있습니다 합니다 **조건 편집** 예외 설정 대화 상자에서 아이콘의 오른쪽 클릭 메뉴를 사용 하 여는 예외입니다.) 현재 지원 되는 조건을 포함 하거나 제외할 예외에 대 한 모듈 이름을 포함 합니다.

    ![예외 조건을](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- 대화 상자 자세한를 연결 해야 하는 프로세스를 신속 하 게 파악할 수 있는 새 검색 기능을 포함 하는 프로세스에 연결 합니다.

    ![검색 프로세스에 연결](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch")

이러한 새 기능에 대 한 자세한 내용은 참조는 [에 대 한 릴리스 정보 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](/visualstudio/releasenotes/vs2017-relnotes)합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 디버깅](../debugger/index.md)
- [디버거 소개](../debugger/debugger-feature-tour.md)