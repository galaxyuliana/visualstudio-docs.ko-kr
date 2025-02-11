---
title: Visual Studio 2019의 새로운 기능
titleSuffix: ''
description: Visual Studio 2019의 새로운 기능을 알아보세요.
ms.date: 07/23/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 1f4a055f62fe76c701858f82b4778f7a3b19fa0a
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918778"
---
# <a name="whats-new-in-visual-studio-2019"></a>Visual Studio 2019의 새로운 기능

**[16.2 릴리스](/visualstudio/releases/2019/release-notes/)용으로 업데이트됨**

>[!div class="button"]
>[Visual Studio 2019 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

Visual Studio 2019를 사용하면 모든 개발자, 앱 및 플랫폼을 위한 업계 최고의 도구와 서비스가 제공됩니다. Visual Studio를 처음 사용하는 초보자든, 수년간 사용한 숙련자든 간에 이 새로운 버전에는 유용한 많은 기능이 있습니다.

다음은 새로운 기능에 대한 간략한 요약입니다.

* **[개발](#develop)** : 향상된 성능, 인스턴트 코드 정리, 더 나은 검색 결과를 사용하여 계속 집중하고 생산성을 유지합니다.
* **[공동 작업](#collaborate)** : Git 우선 워크플로, 실시간 편집 및 디버깅, Visual Studio에서 바로 코드 검토를 사용하여 자연스럽게 협업합니다.
* **[디버그](#debug)** : 특정 값을 강조 표시하여 탐색하고, 메모리 사용을 최적화하며, 애플리케이션 실행의 자동 스냅샷을 만듭니다.

이 버전에 포함된 모든 새로운 기능의 전체 목록은 [릴리스 정보](/visualstudio/releases/2019/release-notes/)를 참조하세요.

## <a name="develop"></a>개발

새로운 기능을 사용하여 시간을 절약하는 방법에 대해 자세히 알아보려면 다음 비디오를 보세요. <br><br>*비디오 길이: 3.00분*

> [!VIDEO https://www.youtube.com/embed/n5sJ4EewKGk]

### <a name="improved-search"></a>향상된 검색

이전에는 빠른 실행이라고 불린 새로운 검색 환경은 더 빠르고 더 효율적입니다. 이제 사용자가 입력할 때 검색 결과가 동적으로 표시됩니다. 그리고 검색 결과에 명령의 바로 가기 키가 포함되는 경우가 많으므로 훨씬 간편하게 기억해 두었다가 나중에 사용할 수 있습니다.

   ![Visual Studio 2019의 새로운 검색 환경 애니메이션](media/vs-2019/new-search-feature.gif)

새 퍼지 검색 논리는 오타와 관계없이 필요한 내용을 찾습니다. 따라서 명령, 설정, 설명서, 기타 유용한 항목을 찾는지와 관계없이 새로운 검색 기능을 사용하면 간편하게 원하는 내용을 찾을 수 있습니다.

### <a name="refactorings"></a>리팩터링

C#에서 코드 구성을 더 쉽게 만드는 매우 유용한 새로운 리팩터링이 많이 있습니다. 전구 아이콘의 제안으로 표시되며 인터페이스 또는 기본 클래스로 멤버 이동, 폴더 구조와 일치하도록 네임스페이스 조정, foreach-loops를 Linq 쿼리로 변환하는 등의 작업이 포함됩니다.

   ![Visual Studio 2019의 리팩터링 환경 애니메이션](media/vs-2019/refactorings.gif)

**Ctrl+.** 를 누르고 수행할 작업을 선택하여 리팩터링을 호출하면 됩니다.

### <a name="intellicode"></a>IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/)는 AI(인공 지능)를 사용하여 소프트웨어 개발 작업을 개선합니다. IntelliCode는 각각 100개 이상의 별이 달린 GitHub의 오픈 소스 프로젝트 2,000개를 학습하여 권장 사항을 생성합니다.

![Visual Studio 2019의 IntelliCode 애니메이션](media/vs-2019/IntelliCode.gif)

Visual Studio IntelliCode로 생산성을 높이는 몇 가지 방법이 있습니다.

* 컨텍스트 인식 코드 완성본 제공
* 개발자에게 팀의 패턴 및 스타일을 준수하도록 안내
* 찾기 어려운 코드 문제 발견
* 정말 중요한 영역으로 주의를 끌어 코드 검토에 집중

IntelliCode를 Visual Studio용 확장을 처음 소개할 때는 C#만 지원했습니다. 이제 **16.1부터** C# 및 XAML 지원도 “기본으로” 추가되었습니다. (그러나 C++ 및 TypeScript/JavaScript에 대한 지원은 계속 미리 보기 상태입니다.)

C#을 사용하는 분들을 위해 사용자 고유의 코드에서 사용자 지정 모델을 학습하는 기능도 추가되었습니다.

IntelliCode에 대한 자세한 내용은 [IntelliCode 및 미리 보기의 일반 제공 발표](https://devblogs.microsoft.com/visualstudio/announcing-the-general-availability-of-intellicode-plus-a-sneak-peek/) 및 [Visual Studio IntelliCode로 코드는 더 많이, 스크롤은 적게](https://devblogs.microsoft.com/visualstudio/code-more-scroll-less-with-visual-studio-intellicode/) 블로그 게시물을 참조하세요.

### <a name="code-cleanup"></a>코드 정리

새로운 문서 상태 표시기와 새로운 코드 정리 명령이 쌍으로 제공됩니다. 이 새 명령을 사용하여 단추 클릭 한 번으로 경고 및 제한 사항을 식별하고 수정할 수 있습니다.

정리는 코드를 포맷하고 [현재 설정](code-styles-and-code-cleanup.md) 및 [.editorconfig 파일](create-portable-custom-editor-options.md)에서 제안하는 코드 수정 사항을 적용합니다.

   ![Visual Studio 2019의 새 코드 정리 컨트롤 스크린샷](media/vs-2019/code-cleanup-profile.png)

수정 도구 컬렉션을 프로필로 저장할 수도 있습니다. 예를 들어 코딩하는 동안 자주 적용하는 작은 대상 지정 수정 도구 세트가 있고 코드 검토 전에 적용할 다른 포괄적인 수정 도구 세트가 있는 경우 이러한 여러 작업을 처리하도록 프로필을 구성할 수 있습니다.

   ![Visual Studio 2019의 코드 정리 구성 컨트롤 스크린샷](media/vs-2019/code-cleanup-profile-configure.png)

### <a name="per-monitor-aware-pma-rendering"></a>PMA(모니터별 인식) 렌더링

여러 디스플레이 배율 인수를 사용하여 구성된 모니터를 사용하거나, 디스플레이 배율 인수가 주 디바이스와 다른 머신에 원격으로 연결하는 경우 Visual Studio가 흐리게 보이거나 잘못된 배율로 렌더링될 수 있습니다.

Visual Studio 2019 릴리스부터 Visual Studio를 PMA(모니터별 인식) 애플리케이션으로 만들게 됩니다. 이제 Visual Studio에서 사용하는 표시 배율에 관계없이 정확하게 렌더링됩니다.

   ![Visual Studio 2019의 PMA(모니터별 인식) 렌더링](media/vs-2019/pma-dpi-scaling.png)

자세한 내용은 [Better multi-monitor experience with Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/a-better-multi-monitor-experience-with-visual-studio-2019/)(Visual Studio 2019를 사용하여 다중 모니터 경험 향상) 블로그 게시물을 참조하세요.

### <a name="test-explorer"></a>테스트 탐색기

**16.2의 새로운 기능**: 테스트 탐색기에서 큰 테스트 집합의 더욱 효율적인 처리, 편리한 필터링, 검색하기 쉬운 명령, 탭 재생 목록 보기, 사용자가 표시되는 테스트 정보를 세부적으로 조정할 수 있는 사용자 지정 가능한 열 등을 제공하도록 업데이트했습니다.

   ![테스트 탐색기에서 향상된 사용자 인터페이스를 보여 주는 스크린샷](media/vs-2019/test-explorer-ui.png)

## <a name="collaborate"></a>공동 작업

협력하여 문제를 해결하는 방법에 대한 자세한 내용을 보려면 다음 비디오를 보세요. <br><br>*비디오 길이: 4.22분*

> [!VIDEO https://www.youtube.com/embed/dKLJsiK1QU8]

### <a name="cloud-first-workflow"></a>클라우드 우선 워크플로

Visual Studio 2019를 열면 새 시작 창이 표시됩니다.

   ![Visual Studio 2019의 새 시작 창 스크린샷](media/vs-2019/start-window-dark.png)

시작 창은 신속하게 코딩할 수 있는 몇 가지 옵션을 제공합니다. 먼저 리포지토리에서 코드를 복제하거나 체크 아웃하는 옵션이 배치되었습니다.

   ![Visual Studio 2019의 ‘Git 우선’ 환경 애니메이션](media/vs-2019/git-first.gif)

시작 창에는 프로젝트 또는 솔루션을 여는 옵션, 로컬 폴더를 여는 옵션 또는 새 프로젝트를 만드는 옵션도 포함되어 있습니다.

자세한 내용은 [코드 가져오기: 새 Visual Studio 시작 창 디자인 방법](https://devblogs.microsoft.com/visualstudio/get-to-code-how-we-designed-the-new-visual-studio-start-window/) 블로그 게시물을 참조하세요.

### <a name="live-share"></a>Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/)는 Visual Studio 내에서 바로 코드베이스와 컨텍스트를 팀원과 공유하고 즉각적인 양방향 협업을 수행할 수 있는 개발자 서비스입니다. 실시간 공유를 사용하면 귀하가 공유한 프로젝트를 팀원이 원활하고 안전하게 읽고, 탐색하고, 편집하고, 디버깅할 수 있습니다.

그리고 Visual Studio 2019를 사용하면 이 서비스가 기본적으로 설치됩니다.

![Visual Studio 2019의 Live Share 협업 기능을 보여 주는 애니메이션](media/vs-2019/live-share.gif)

자세한 내용은 [Visual Studio Live Share for real-time code reviews and interactive education](https://devblogs.microsoft.com/visualstudio/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/)(실시간 코드 검토 및 대화형 교육을 위한 Visual Studio Live Share) 블로그 게시물 및 [Live Share now included with Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/live-share-now-included-with-visual-studio-2019/)(이제 Live Share가 Visual Studio 2019에 포함됨) 블로그 게시물을 참조하세요.

### <a name="integrated-code-reviews"></a>통합된 코드 검토

다운로드하여 Visual Studio 2019와 함께 사용할 수 있는 새로운 확장이 곧 도입됩니다. 이 새로운 확장을 사용하면 Visual Studio를 벗어나지 않고도 팀의 끌어오기 요청을 검토, 실행 및 디버그할 수 있습니다. GitHub 및 Azure DevOps 리포지토리 둘 다에서 코드를 지원합니다.

   ![Visual Studio 2019의 새 시작 창 스크린샷](media/vs-2019/pr-experience.png)

자세한 내용은 [Visual Studio 끌어오기 요청 확장을 사용하여 코드 검토](https://devblogs.microsoft.com/visualstudio/code-reviews-using-the-visual-studio-pull-requests-extension/) 블로그 게시물을 참조하세요.

## <a name="debug"></a>디버그

디버그하는 동안 정확한 대상 지정으로 목표를 달성하는 방법에 대한 자세한 내용을 보려면 다음 비디오를 보세요. <br><br>*비디오 길이: 3.54분*

> [!VIDEO https://www.youtube.com/embed/hr72Fs8n_9c]

### <a name="performance-gains"></a>성능 효과

한 번-단독 C++ 데이터 중단점을 가져와서 .NET Core 애플리케이션에 맞게 조정했습니다.

   ![Visual Studio 2019의 디버그 데이터 중단점을 보여 주는 애니메이션](media/vs-2019/debug-data-breakpoints.gif)

따라서 C++에서 코딩하든, .NET Core에서 코딩하든 간에 일반 중단점을 배치하는 것보다 데이터 중단점을 사용하는 것이 좋습니다. 데이터 중단점은 전역 개체가 수정되거나 목록에 추가 또는 제거되는 위치 찾기와 같은 시나리오에도 유용합니다.

또한 대규모 애플리케이션을 개발하는 C++ 개발자인 경우 Visual Studio 2019에서는 메모리 관련 문제없이 애플리케이션을 디버그할 수 있는 Out of Process 기호를 만들었습니다.

### <a name="search-while-debugging"></a>디버그하는 동안 검색

아마도 다들 이전에 조사식 창을 들여다보며 값 세트 중에서 문자열을 찾아본 경험이 있을 것입니다. Visual Studio 2019에서는 원하는 개체 및 값을 쉽게 찾을 수 있도록 조사식, 로컬 및 자동 창에 검색을 추가했습니다.

   ![Visual Studio 2019의 디버그 검색 창을 보여 주는 애니메이션](media/vs-2019/debug-window-search.gif)

조사식, 로컬 및 자동 창 내에서 값을 표시하는 방법도 지정할 수 있습니다.  아무 창에서 항목 중 하나를 두 번 클릭하고 쉼표(",")를 추가하면 사용 가능한 포맷 지정자 드롭다운 목록에 액세스할 수 있으며, 각각에는 의도하는 효과에 대한 설명이 포함되어 있습니다.

   ![Visual Studio 2019의 새로운 조사식 창 및 포맷 값 기능](media/search-watch-window.png)

자세한 내용은 [Visual Studio 2019의 향상된 기능: 조사식, 자동 및 지역 Windows의 개체와 속성 검색](https://devblogs.microsoft.com/visualstudio/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/) 블로그 게시물을 참조하세요.

### <a name="snapshot-debugger"></a>스냅샷 디버거

클라우드의 앱 실행 스냅샷을 가져와 진행 상황을 정확하게 확인합니다. 이 기능은 Visual Studio Enterprise에서만 사용할 수 있습니다.

   ![Visual Studio 2019 Enterprise의 스냅샷 디버거를 보여 주는 애니메이션](media/vs-2019/snapshot-debugger.gif)

Azure VM에서 실행되는 ASP.NET(Core 및 데스크톱) 애플리케이션을 대상으로 지정하는 지원이 추가되었습니다. 또한 Azure Kubernetes Service에서 실행되는 애플리케이션에 대한 지원이 추가되었습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

자세한 내용은 [스냅샷 디버거를 사용하여 라이브 ASP.NET Azure 앱 디버그](../debugger/debug-live-azure-applications.md) 페이지와 [Introducing Time Travel Debugging for Visual Studio Enterprise 2019](https://devblogs.microsoft.com/visualstudio/introducing-time-travel-debugging-for-visual-studio-enterprise-2019/)(Visual Studio Enterprise 2019의 시간 이동 디버깅 소개) 블로그 게시물을 참조하세요.

### <a name="microsoft-edge-insider-support"></a>Microsoft Edge Insider 지원

**16.2의 새로운 기능**: JavaScript 애플리케이션에서 중단점을 설정하고 [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) 브라우저를 사용하여 디버그 세션을 시작합니다. 이렇게 하면 Visual Studio 내에서 애플리케이션 JavaScript를 통해 작업을 진행할 수 있게 디버깅이 활성화된 새 브라우저 창이 Visual Studio에서 실행됩니다.

   ![브라우저에서 JavaScript 코드 렌더링을 보여 주는 스크린샷](media/vs-2019/edge-chromium-breakpoint.png)

## <a name="whats-next"></a>새로운 기능

Visual Studio 2019는 개발 환경을 훨씬 더 좋게 만들어 줄 수 있는 새 기능으로 자주 업데이트됩니다. 최신 혁신 기능을 자세히 알아보려면 [Visual Studio 블로그](https://devblogs.microsoft.com/visualstudio/)를 확인하세요. 미리 보기에서 현재까지 릴리스된 내용에 대한 기록은 [미리 보기 릴리스 노트](/visualstudio/releases/2019/release-notes-preview/)를 살펴보세요.

Visual Studio 2019에서 진행 중인 다른 기능에 대해 더 알고 싶은가요? [Visual Studio 로드맵](/visualstudio/productinfo/vs-roadmap/)을 참조하세요.

## <a name="give-us-feedback"></a>피드백 보내기

피드백을 보낼 때는 Visual Studio 팀에 피드백을 보내는 이유도 함께 알려 주세요. Microsoft는 고객 여러분의 피드백을 소중하게 생각하며, Microsoft에서 추진하는 업무에 큰 역할을 합니다.

* Visual Studio 개선 방안에 대한 의견이 있는 분들은 [기능 제안](suggest-a-feature.md) 도구를 사용하여 의견을 보내주세요.

* 시스템 중단, 충돌 또는 기타 성능 문제가 발생하는 경우 [문제 보고](how-to-report-a-problem-with-visual-studio.md) 도구를 사용하여 간편하게 재현 단계 및 지원 파일을 공유할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [Visual Studio 2019 릴리스 정보](/visualstudio/releases/2019/release-notes/)
* [Visual Studio 2019 SDK의 새로운 기능](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [Mac용 Visual Studio 2019 릴리스 정보](/visualstudio/releasenotes/vs2019-mac-relnotes/)
* [Microsoft 빌드 2019 회의](https://www.microsoft.com/build)
* [Microsoft Connect(); 2018 회의](https://www.microsoft.com/connectevent)
