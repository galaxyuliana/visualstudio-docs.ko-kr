---
title: 정리 프로젝트 솔루션 빌드
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.BuildProjectPicker
- vs.batchbuild
helpviewer_keywords:
- Clean Solution command
- builds [Visual Studio], managing
- solution build configurations, starting
- Build Solution command
- project build configurations, starting
- build configurations, starting
- project build configurations, dependencies
- Rebuild Solution command
- solution build configurations, build order
- builds [Visual Studio], preparing
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d447d82815046aba6383c2467c2b44c5b7d0d0f0
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685711"
---
# <a name="building-and-cleaning-projects-and-solutions-in-visual-studio"></a>Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 절차에 따라 솔루션에 포함된 프로젝트 또는 프로젝트 항목의 전체 또는 일부를 빌드, 다시 빌드 또는 정리할 수 있습니다. 단계별 자습서는 [연습: 애플리케이션 빌드](../ide/walkthrough-building-an-application.md)를 참조하세요.

> [!NOTE]
> 사용 중인 Visual Studio 버전의 UI는 활성 설정에 따라 이 항목의 설명과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴를 열고 **설정 가져오기 및 내보내기**를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.

## <a name="to-build-rebuild-or-clean-an-entire-solution"></a>전체 솔루션을 빌드, 다시 빌드 또는 정리하려면

1. **솔루션 탐색기**에서 솔루션을 선택하거나 엽니다.

2. 메뉴 모음에서 **빌드**를 선택하고 다음 명령 중 하나를 선택합니다.

    - 가장 최근 빌드 이후 변경된 프로젝트 파일 및 구성 요소만 컴파일하려면 **빌드** 또는 **솔루션 빌드**를 선택합니다.

        > [!NOTE]
        > 솔루션에 둘 이상의 프로젝트가 포함된 경우에는 **빌드** 명령이 **솔루션 빌드**로 표시됩니다.

    - 솔루션을 "정리"한 다음 모든 프로젝트 파일과 구성 요소를 빌드하려면 **솔루션 다시 빌드**를 선택합니다.

    - 중간 파일과 출력 파일을 모두 삭제하려면 **솔루션 정리**를 선택합니다. 그런 다음 프로젝트 및 구성 요소 파일만 유지하여 중간 파일과 출력 파일의 새 인스턴스를 빌드할 수 있습니다.

## <a name="to-build-or-rebuild-a-single-project"></a>단일 프로젝트를 빌드 또는 다시 빌드하려면

1. **솔루션 탐색기**에서 프로젝트를 선택하거나 엽니다.

2. 메뉴 모음에서 **빌드**를 선택한 다음, _ProjectName_ **빌드** 또는 _ProjectName_ **다시 빌드**를 선택합니다.

    - 가장 최근 빌드 이후 변경된 프로젝트 구성 요소만 빌드하려면 _ProjectName_ **빌드**를 선택합니다.

    - 프로젝트를 "정리"한 다음, 프로젝트 파일과 모든 프로젝트 구성 요소를 빌드하려면 _ProjectName_ **다시 빌드**를 선택합니다.

## <a name="to-build-only-the-startup-project-and-its-dependencies"></a>시작 프로젝트 및 해당 종속성만 빌드하려면

1. 메뉴 모음에서 **도구**, **옵션**을 선택합니다.

2. **옵션** 대화 상자에서 **프로젝트 및 솔루션** 노드를 확장하고 **빌드 및 실행** 페이지를 선택합니다.

    **옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행**이 열립니다.

3. **실행할 때 시작 프로젝트와 종속성만 빌드** 확인란을 선택합니다.

    이 확인란을 선택하면 다음 단계 중 하나를 수행할 때 현재 시작 프로젝트와 해당 종속성만 빌드됩니다.

   - 메뉴 모음에서 선택 **디버깅할** > **디버깅 시작** (F5).

   - 메뉴 모음에서 선택 **빌드합니다** > **솔루션 빌드** (CTRL + SHIFT + B).

     이 확인란의 선택을 취소하면 이전 명령 중 하나를 실행할 때 모든 프로젝트, 해당 종속성 및 솔루션 파일이 빌드됩니다. 이 확인란은 기본적으로 선택되어 있지 않습니다.

## <a name="to-build-only-the-selected-visual-c-project"></a>선택한 Visual C++ 프로젝트만 빌드하려면

1. [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] 프로젝트를 선택한 다음 메뉴 모음에서 **빌드**, **프로젝트만**, 다음 명령 중 하나를 차례로 선택합니다.

   - *ProjectName***만 빌드**

   - *ProjectName***만 다시 빌드**

   - *ProjectName***만 정리**

   - *ProjectName***만 링크**

     이러한 명령은 프로젝트 종속성 또는 솔루션 파일을 빌드, 다시 빌드, 정리 또는 링크하지 않고 선택한 [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] 프로젝트에만 적용됩니다. 사용 중인 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 버전에 따라 **프로젝트만** 하위 메뉴에 추가 명령이 포함될 수 있습니다.

## <a name="to-compile-multiple-c-project-items"></a>여러 C++ 프로젝트 항목을 컴파일하려면

1. **솔루션 탐색기**에서 작업으로 컴파일할 수 있는 여러 파일을 선택하고 해당 파일 중 하나의 바로 가기 메뉴를 연 다음 **컴파일**을 선택합니다.

     파일에 종속성이 있는 경우 종속성 순서에 따라 파일이 컴파일됩니다. 컴파일 시 사용할 수 없는 미리 컴파일된 헤더가 파일에 필요한 경우 컴파일 작업이 실패합니다. 컴파일 작업은 현재 활성 솔루션 구성을 사용합니다.

## <a name="to-stop-a-build"></a>빌드를 중지하려면

1. 다음 단계 중 하나를 수행합니다.

    - 메뉴 모음에서 **빌드**, **취소**를 선택합니다.

    - Ctrl+Break 키를 선택합니다.

## <a name="see-also"></a>참고자료
 [방법: 보기, 저장 및 빌드 로그 파일을 구성](../ide/how-to-view-save-and-configure-build-log-files.md) [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md) [컴파일 및 빌드](../ide/compiling-and-building-in-visual-studio.md) [빌드 구성 이해](../ide/understanding-build-configurations.md) [디버그 및 릴리스 프로젝트 구성](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e) [C /C++ 빌드 참조](https://msdn.microsoft.com/library/100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d) [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md) [솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)
