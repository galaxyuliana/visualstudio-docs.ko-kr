---
title: Visual Studio 2019의 새로운 기능
titleSuffix: ''
description: Visual Studio 2019의 새로운 기능을 알아보세요.
ms.date: 01/24/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-dev16
ms.topic: conceptual
ms.workload:
- multiple
monikerRange: '>= vs-2017'
ms.openlocfilehash: 9f1d2ba67739dd5349a1a361744543089900a371
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2019
ms.locfileid: "55090109"
---
# <a name="whats-new-in-visual-studio-2019-preview"></a>Visual Studio 2019 Preview의 새로운 기능

**[미리 보기 2 릴리스](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)의 업데이트**

>[!div class="button"]
>[미리 보기 다운로드](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+preview)

Visual Studio 2019 미리 보기에는 개발자 생산성 및 팀 공동 작업을 최적화하는 여러 개선된 기능이 포함되어 있습니다. Visual Studio를 처음 접하는 분이든 수년째 사용 중인 분이든, 간단한 프로젝트 만들기 및 코드 상태 관리부터 팀 및 오픈 소스 공동 작업 워크플로까지 개발 수명 주기의 모든 면에서 기능을 활용할 수 있습니다.<br/><br/>

>[!VIDEO https://channel9.msdn.com/Events/Connect/Microsoft-Connect--2018/D190/player]

Visual Studio가 제공하는 장점은 다음과 같습니다.

* **[개인 및 팀 생산성](#personal-and-team-productivity)**. 모든 사람에게 가장 중요한 것은 생산성입니다.
* **[최신 개발 지원](#modern-development-support)**. 현재 프로젝트 및 향후 솔루션을 지원합니다.
* **[지속적인 혁신](#continuous-innovation)**. 코드에 인텔리전트 클라우드 기반 지원이 제공됩니다.

> [!NOTE]
> Visual Studio 2019 미리 보기의 새로운 특징 및 기능의 전체 목록은 [릴리스 정보](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)를 참조하세요.

## <a name="personal-and-team-productivity"></a>개인 및 팀 생산성

Visual Studio의 모든 릴리스에서 가장 중요한 것은 당연히 성능 향상이지만, 생산성 향상 역시 그에 못지 않게 중요합니다. 다음과 같은 방법으로 생산성을 높일 수 있습니다.

### <a name="new-start-window"></a>새로운 시작 창

Visual Studio 2019를 열면 가장 먼저 보이는 것이 새로운 시작 창입니다.

   ![Visual Studio 2019의 새로운 시작 창](media/start-window.png)

새로운 시작 창은 코드를 복제 또는 체크 아웃하고, 프로젝트 또는 솔루션을 열고, 로컬 폴더를 열고, 새 프로젝트를 만드는 옵션을 제공합니다. 이러한 옵션을 간단한 대화 상자에 제공하므로 Visual Studio 초보자부터 고급 사용자까지 모든 사용자가 신속하게 코드를 가져올 수 있습니다.

자세한 내용은 [코드 가져오기: 새 Visual Studio 시작 창 디자인 방법](https://blogs.msdn.microsoft.com/visualstudio/2018/12/13/get-to-code-how-we-designed-the-new-visual-studio-start-window/) 블로그 게시물을 참조하세요.

### <a name="better-search"></a>향상된 검색

이전에는 빠른 실행이라고 불린 새로운 검색 환경은 더 빠르고 더 효율적입니다. 이제 사용자가 입력할 때 검색 결과가 동적으로 표시됩니다. 그리고 검색 결과에 명령의 키보드 바로 가기 키가 포함되므로 훨씬 간편하게 기억해 두었다가 나중에 사용할 수 있습니다.

   ![Visual Studio 2019의 새로운 검색 기능](media/search-feature.png)

명령, 설정, 설명서, 기타 유용한 정보 등을 찾을 때 새로운 검색 기능을 사용하면 간편하게 원하는 내용을 찾을 수 있습니다.

### <a name="one-click-code-cleanup"></a>원클릭 코드 정리

새로운 문서 상태 표시기와 새로운 코드 정리 명령이 쌍으로 제공됩니다. 이 새 명령을 사용하여 단추 클릭 한 번으로 경고 및 제한 사항을 식별하고 수정할 수 있습니다.

   ![Visual Studio 2019의 새로운 코드 정리 기능](media/code-cleanup.png)

정리는 코드를 포맷하고 [현재 설정](code-styles-and-quick-actions.md), [.editorconfig 파일](create-portable-custom-editor-options.md) 또는 [Roslyn 분석기](../code-quality/roslyn-analyzers-overview.md)가 제안하는 코드 수정 사항을 적용합니다.

### <a name="debugger-improvements"></a>향상된 디버거

#### <a name="search-within-a-watch-window-and-format-watch-values"></a>조사식 창 내에서 검색하고 조사식 값 포맷

아마도 다들 이전에 조사식 창을 들여다보며 값 세트 중에서 문자열을 찾아본 경험이 있을 것입니다. Visual Studio 2019 미리 보기에서는 원하는 개체 및 값을 쉽게 찾을 수 있도록 조사식, 로컬 및 자동 창에 검색을 추가했습니다.

조사식, 로컬 및 자동 창 내에서 값을 표시하는 방법도 지정할 수 있습니다.  아무 창에서 항목 중 하나를 두 번 클릭하고 쉼표(",")를 추가하면 사용 가능한 포맷 지정자 드롭다운 목록에 액세스할 수 있으며, 각각에는 의도하는 효과에 대한 설명이 포함되어 있습니다.

   ![Visual Studio 2019의 새로운 조사식 창 및 포맷 값 기능](media/search-watch-window.png)

### <a name="visual-studio-live-share"></a>Visual Studio Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/)는 Visual Studio 내에서 바로 코드베이스와 컨텍스트를 팀원과 공유하고 즉각적인 양방향 공동 작업을 수행할 수 있는 개발자 서비스입니다. 실시간 공유를 사용하면 귀하가 공유한 프로젝트를 팀원이 원활하고 안전하게 읽고, 탐색하고, 편집하고, 디버깅할 수 있습니다.

Visual Studio 2019 미리 보기를 사용하면 이 서비스가 기본적으로 설치됩니다.

자세한 내용은 [실시간 코드 검토 및 대화형 교육을 위한 Visual Studio Live Share](https://blogs.msdn.microsoft.com/visualstudio/2018/12/06/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/) 블로그 게시물을 참조하세요.

## <a name="modern-development-support"></a>최신 개발 지원

### <a name="manage-pull-requests-prs-from-the-ide"></a>IDE에서 끌어오기 요청(PR) 관리

다운로드하여 Visual Studio 2019 미리 보기와 함께 사용할 수 있는 새로운 확장이 곧 도입됩니다. 이 새로운 확장을 사용하면 Visual Studio IDE[(통합 개발 환경)](../get-started/visual-studio-ide.md)를 벗어나지 않고도 팀의 끌어오기 요청을 검토, 실행 및 디버그할 수 있습니다. 현재 Azure Repos에서 코드를 지원하고 있지만, GitHub를 지원하고 전반적인 환경을 개선하기 위해 확장할 예정입니다.

지금 시작하려면 Visual Studio Marketplace에서 [Visual Studio에 대한 끌어오기 요청](https://aka.ms/pr4vs) 확장을 다운로드하세요.

### <a name="develop-with-net-core-3-preview-1"></a>.NET Core 3 Preview 1을 사용하여 개발

Visual Studio 2019의 미리 보기 릴리스는 모든 플랫폼에서 [.NET Core 3](http://aka.ms/netcore3preview1) 애플리케이션 빌드를 지원합니다. 앞으로도 계속해서 플랫폼 간 C++ 개발뿐 아니라 Xamarin을 사용한 iOS 및 Android용 .NET 모바일 개발을 지원하고 개선할 것입니다.

   ![Visual Studio 2019에서 .NET Core 3 Preview 1을 사용하여 앱 개발](media/dot-net-core-three-dev.png)

## <a name="continuous-innovation"></a>지속적인 혁신

### <a name="per-monitor-aware-pma-rendering"></a>PMA(모니터별 인식) 렌더링

여러 디스플레이 배율 인수를 사용하여 구성된 모니터를 사용하거나, 디스플레이 배율 인수가 주 디바이스와 다른 머신에 원격으로 연결하는 경우 Visual Studio가 흐리게 보이거나 잘못된 배율로 렌더링될 수 있습니다.

Visual Studio 2019 미리 보기 1 릴리스부터 Visual Studio를 PMA(모니터별 인식) 애플리케이션으로 만들기 위한 첫 번째 단계가 시작됩니다. 사용하는 디스플레이 배율에 관계없이 Visual Studio가 올바르게 렌더링할 수 있도록 기반 작업을 진행 중입니다.

   ![Visual Studio 2019의 PMA(모니터별 인식) 렌더링](media/per-monitor-aware-dpi-scaling.png)

### <a name="visual-studio-intellicode"></a>Visual Studio IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/)는 AI(인공 지능)를 사용하여 소프트웨어 개발 작업을 개선하는 확장 프로그램입니다. IntelliCode는 각각 100개 이상의 별이 달린 GitHub의 오픈 소스 프로젝트 2,000개를 학습하여 권장 사항을 생성합니다.

Visual Studio IntelliCode로 생산성을 높이는 몇 가지 방법이 있습니다.

* 컨텍스트 인식 코드 완성본 제공
* 개발자에게 팀의 패턴 및 스타일을 준수하도록 안내
* 찾기 어려운 코드 문제 발견
* 정말 중요한 영역으로 주의를 끌어 코드 검토에 집중

Visual Studio용 IntelliCode 확장을 처음 소개할 때는 C#만 지원했습니다. 이제 Visual Studio에서 C++ 및 XAML 지원도 추가되었습니다.

C#을 사용하는 분들을 위해 사용자 고유의 코드에서 사용자 지정 모델을 학습하는 기능도 추가되었습니다.

최근 업데이트에 대한 자세한 내용은 [Visual Studio IntelliCode는 더 많은 언어를 지원하고 코드에서 학습](https://blogs.msdn.microsoft.com/visualstudio/2018/12/05/visual-studio-intellicode-supports-more-languages-and-learns-from-your-code/) 블로그 게시물을 참조하세요. 그리고, 확장과 다운로드 방법에 대한 자세한 내용은 Microsoft DevLabs의 [Visual Studio IntelliCode - 미리 보기](https://go.microsoft.com/fwlink/?linkid=872707) 페이지를 참조하세요.

## <a name="give-us-feedback"></a>피드백 보내기

피드백을 보낼 때는 Visual Studio 팀에 피드백을 보내는 이유도 함께 알려 주세요. Microsoft는 고객 여러분의 피드백을 소중하게 생각하며, Microsoft에서 추진하는 업무에 큰 역할을 합니다.

* Visual Studio 개선 방안에 대한 의견이 있는 분들은 [의견 보내기](talk-to-us.md#i-want-to-make-a-suggestion-about-visual-studio-features) 도구를 사용하여 의견을 보내주세요.

* 시스템 중단, 충돌 또는 기타 성능 문제가 발생하는 경우 [문제 보고](talk-to-us.md#i-want-to-report-a-problem-with-visual-studio) 도구를 사용하여 간편하게 재현 단계 및 지원 파일을 공유할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [Visual Studio 2019 릴리스 정보](/visualstudio/releases/2019/release-notes-preview?context=visualstudio/default&contextView=vs-2017)
* [Microsoft Connect(); 2018 회의](https://www.microsoft.com/connectevent)
* [Visual Studio 2017의 새로운 기능](whats-new-visual-studio-2017.md)
