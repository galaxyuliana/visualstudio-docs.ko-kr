---
title: Mac용 Visual Studio에서 여러 시작 프로젝트 설정
description: 이 문서에서는 실행 또는 디버그를 시작할 여러 프로젝트를 설정하는 방법을 설명합니다.
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: 65b44dddfdadcb7ef38332fa35443dbaeededb5d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152917"
---
# <a name="how-to-set-multiple-startup-projects"></a>방법: 여러 시작 프로젝트 설정

Mac용 visual Studio를 사용하면 솔루션을 디버깅하거나 실행할 때 둘 이상의 프로젝트를 시작하는 방법을 지정할 수 있습니다.

## <a name="to-set-multiple-startup-projects"></a>여러 시작 프로젝트를 설정하려면

1.  **Solution Pad**에서 솔루션(최상위 노드)을 선택합니다.

2. 솔루션 노드의 컨텍스트(마우스 오른쪽 단추 클릭) 메뉴를 선택한 다음, **시작 프로젝트 설정...** 을 선택합니다.

   ![시작 프로젝트 컨텍스트 메뉴 설정](media/startup-proj-ctx-menu.png)

3. **솔루션 실행 구성 만들기** 대화 상자가 나타납니다. 이 대화 상자는 솔루션에 대해 솔루션 실행 구성이라는 새 이름을 생성합니다. 원하는 이름을 지정할 수 있으며 기본 이름은 `Multiple Projects`입니다.

   ![솔루션 실행 구성 만들기 대화 상자](media/create-sln-run-config.png)

4. **실행 구성 만들기**를 클릭합니다. **솔루션 옵션** 대화 상자가 열리고 새 솔루션 실행 구성이 선택됩니다.

   ![솔루션 옵션 대화 상자](media/sln-options-run-config-multi-projects.png)

5. Mac용 Visual Studio에서 애플리케이션을 디버깅하거나 실행할 때 시작할 프로젝트를 선택합니다.

   ![구성된 실행 구성이 있는 솔루션 옵션 대화 상자](media/sln-options-run-config-multi-projects-configured.png)

6. **확인**을 클릭합니다. 대화 상자가 닫히고 새 솔루션 실행 구성이 활성 실행 구성으로 설정됩니다.

   ![디버그 또는 실행 시 시작하도록 구성된 여러 프로젝트가 포함된 솔루션](media/startup-project-configured.png) 두 프로젝트 모두 **Solution Pad**의 **볼드**에 있으므로 두 프로젝트가 시작되도록 구성되어 있음을 알 수 있습니다. 도구 모음에서 새 실행 구성은 현재 솔루션 실행 구성으로 구성됩니다.

## <a name="next-steps"></a>다음 단계

- [Mac용 Visual Studio에서 컴파일 및 빌드](compiling-and-building.md)
- [빌드 구성 이해](configurations.md)