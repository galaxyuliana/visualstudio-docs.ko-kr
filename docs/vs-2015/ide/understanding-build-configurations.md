---
title: 빌드 구성 이해 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- SolutionProperties.ActiveConfig
- vs.build.newprojectconfiguration
- vc.proj.configurationsctrl.multipleconfigs
- vs.build.editsolutionconfigurations
- vs.build.editprojectconfigurations
- vs.multipleconfigurations
- vs.build.newsolutionconfiguration
- VS.ConfigurationManager
- VS.MultipleConfig
helpviewer_keywords:
- solution build configurations, about build configurations
- build configurations
- project build configurations
- build configurations, advanced
- projects [Visual Studio], build configuration
- solutions [Visual Studio], build configuration
ms.assetid: 934c727d-3a22-429c-bd13-3552cecf2e24
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f3b4898166ec24cb429463f55f8b166056123e78
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65683873"
---
# <a name="understanding-build-configurations"></a>빌드 구성 이해
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

다양한 종류의 빌드에서 사용할 솔루션 및 프로젝트 속성에 대한 여러 구성을 저장할 수 있습니다. 구성을 만들거나, 선택하거나, 수정하거나, 삭제하려면 **구성 관리자**를 사용합니다. 구성 관리자를 열려면 메뉴 모음에서 **빌드**, **구성 관리자**를 선택하거나 **빠른 실행** 상자에 **구성**을 입력합니다. **표준** 도구 모음에서 **솔루션 구성** 목록을 사용하여 구성을 선택하거나 **구성 관리자**를 열 수도 있습니다.  
  
> [!NOTE]
> 도구 모음에서 솔루션 구성 설정을 찾을 수 없고 **구성 관리자**에 액세스할 수 없으면 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 개발 설정을 적용할 수 있습니다. 자세한 내용은 [방법: Visual Basic 개발자 설정 적용 하 여 구성 관리](../ide/how-to-manage-build-configurations-with-visual-basic-developer-settings-applied.md)합니다.  
  
 기본적으로 디버그 및 릴리스 구성은 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 템플릿을 사용하여 만든 프로젝트에 포함됩니다. 디버그 구성은 앱의 디버깅을 지원하고 릴리스 구성은 배포할 수 있는 앱 버전을 빌드합니다. 자세한 내용은 [방법: 디버그 및 릴리스 구성 설정](../debugger/how-to-set-debug-and-release-configurations.md)을 참조하세요. 사용자 지정 솔루션 구성 및 프로젝트 구성을 만들 수도 있습니다. 자세한 내용은 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)을 참조하세요.  
  
## <a name="solution-configurations"></a>솔루션 구성  
 솔루션 구성은 솔루션에 있는 프로젝트를 빌드하고 배포하는 데 사용할 방법을 지정합니다. 솔루션 구성을 수정하거나 새 구성을 정의하려면 **구성 관리자**의 **활성 솔루션 구성**에서 **편집** 또는 **새로 만들기**를 선택합니다.  
  
 솔루션 구성에서 **프로젝트 컨텍스트** 상자의 각 항목은 솔루션에 있는 프로젝트를 나타냅니다. **활성 솔루션 구성** 및 **활성 솔루션 플랫폼**의 모든 조합에 대해 각 프로젝트가 사용되는 방법을 설정할 수 있습니다. (솔루션 플랫폼에 대한 자세한 내용은 [빌드 플랫폼 이해](../ide/understanding-build-platforms.md)를 참조하세요.)  
  
> [!NOTE]
> 새 솔루션 구성을 정의하고 **새 프로젝트 구성 만들기** 확인란을 선택하면 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 모든 프로젝트에 새 구성이 자동으로 할당됩니다. 마찬가지로, 새 솔루션 플랫폼을 정의하고 **새 프로젝트 플랫폼 만들기** 확인란을 선택하면 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 에서 모든 프로젝트에 새 플랫폼이 자동으로 할당됩니다. 또한 새 플랫폼을 대상으로 하는 프로젝트를 추가하면 Visual Studio에서 해당 플랫폼이 솔루션 플랫폼 목록에 추가되고 모든 프로젝트에 할당됩니다.  
>   
> 각 프로젝트에 대한 설정은 여전히 수정할 수 있습니다.  
  
 활성 솔루션 구성도 IDE에 컨텍스트를 제공합니다. 예를 들어 프로젝트 작업을 진행 중인데 이 프로젝트가 모바일 디바이스용으로 빌드될 것이라고 구성에 지정되어 있으면, 모바일 디바이스 프로젝트에 사용할 수 있는 항목만 **도구 상자**에 표시됩니다.  
  
## <a name="project-configurations"></a>프로젝트 구성  
 빌드 시 사용할 속성을 지정할 때는 구성과 프로젝트가 대상으로 하는 플랫폼이 함께 사용됩니다. 프로젝트에서는 각 구성 및 플랫폼 조합에 대해 서로 다른 속성 정의 집합을 지정할 수 있습니다. 프로젝트의 속성을 수정하려면 해당 속성 페이지를 사용합니다. (**솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.)  
  
 각 프로젝트 구성에 대해 필요에 따라 구성에 종속된 속성을 정의할 수 있습니다. 예를 들어 특정 빌드에 대해 포함할 프로젝트 항목, 만들 출력 파일, 출력 파일을 넣을 위치 및 출력 파일이 최적화되는 방법을 설정할 수 있습니다.  
  
 프로젝트 구성이 크게 다를 수 있습니다. 예를 들어 한 구성의 속성에 해당 출력 파일이 최소한의 공간만 차지하도록 최적화되어야 함이 지정되어 있지만 다른 구성에는 해당 실행 파일이 최대 속도로 실행되도록 지정되어 있을 수 있습니다.  
  
 프로젝트 구성은 팀에서 공유할 수 있도록 사용자별이 아니라 솔루션별로 저장됩니다.  
  
 프로젝트 종속성이 구성과 무관하더라도 활성 솔루션 구성에 지정된 프로젝트만 빌드됩니다.  
  
## <a name="how-visual-studio-assigns-project-configurations"></a>Visual Studio가 프로젝트 구성을 할당하는 방법  
 새 솔루션 구성을 정의하고 기존 구성에서 설정을 복사하지 않으면 Visual Studio가 다음 기준을 사용하여 기본 프로젝트 구성을 할당합니다. 기준은 표시된 순서대로 평가됩니다.  
  
1. 프로젝트에 새 솔루션 구성의 이름과 정확히 일치하는 구성 이름(*\<구성 이름> \<플랫폼 이름>*)이 있으면 해당 구성이 할당됩니다. 구성 이름은 대/소문자를 구분하지 않습니다.  
  
2. 프로젝트에 구성 이름 부분이 새 솔루션 구성과 일치하는 구성 이름이 지정되어 있으면 플랫폼 부분이 일치하는지 여부와 관계없이 해당 구성이 할당됩니다.  
  
3. 일치하는 부분이 없으면 프로젝트에 나열된 첫 번째 구성이 할당됩니다.  
  
## <a name="how-visual-studio-assigns-solution-configurations"></a>Visual Studio가 솔루션 구성을 할당하는 방법  
 프로젝트 구성을 만들고(**구성 관리자**에서 해당 프로젝트의 **구성** 열에 있는 드롭다운 메뉴의 **새로 만들기** 선택) **새 솔루션 구성 만들기** 확인란을 선택하면 Visual Studio가 각 지원 플랫폼에서 프로젝트를 빌드하기 위해 이름이 같은 솔루션 구성을 찾습니다. 경우에 따라 Visual Studio는 기존 솔루션 구성의 이름을 바꾸거나 새 구성을 정의합니다.  
  
 Visual Studio는 다음 기준을 사용하여 솔루션 구성을 할당합니다.  
  
- 프로젝트 구성이 플랫폼을 지정하지 않거나 하나의 플랫폼만 지정하는 경우 새 프로젝트 구성과 이름이 일치하는 솔루션 구성이 검색되거나 추가됩니다. 이 솔루션 구성의 기본 이름은 플랫폼 이름을 포함하지 않으며 *\<<프로젝트 구성 이름>* 양식을 사용합니다.  
  
- 프로젝트가 여러 플랫폼을 지원하는 경우 지원되는 각 플랫폼에 대해 솔루션 구성이 검색되거나 추가됩니다. 각 솔루션 구성의 이름은 프로젝트 구성 이름과 플랫폼 이름을 모두 포함하며 *\<프로젝트 구성 이름> \<플랫폼 이름>* 양식입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 응용 프로그램 빌드](../ide/walkthrough-building-an-application.md)   
 [컴파일 및 빌드](../ide/compiling-and-building-in-visual-studio.md)   
 [솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)   
 [C/C++ 빌드 참조](https://msdn.microsoft.com/library/100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d)   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)
