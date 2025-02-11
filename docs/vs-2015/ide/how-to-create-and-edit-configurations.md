---
title: '방법: 구성 만들기 및 편집 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- solution build configurations, editing
- build configurations, creating
- solution build configurations, creating
- build configurations, editing
- builds [Visual Studio], setting up
- property pages
- Configuration Manager
- project build configurations, creating
- project build configurations, editing
ms.assetid: 19be121c-148e-4ece-bbfc-d20b08cfc3f7
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 35cda86854bede07c8f1d4830f05607b7fab3643
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680405"
---
# <a name="how-to-create-and-edit-configurations"></a>방법: 구성 만들기 및 편집
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

솔루션에 대한 여러 가지 빌드 구성을 만들 수 있습니다. 예를 들어 테스터가 문제를 찾고 해결하는 데 사용할 수 있는 디버그 빌드를 구성할 수 있고, 다른 고객에게 배포할 수 있는 다양한 종류의 빌드를 구성할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="creating-build-configurations"></a>빌드 구성 만들기  
 **구성 관리자** 대화 상자를 사용하여 기존 빌드 구성을 선택 또는 수정할 수 있고, 새 빌드 구성을 만들 수도 있습니다.  
  
#### <a name="to-open-the-configuration-manager-dialog-box"></a>[구성 관리자] 대화 상자를 열려면  
  
- **솔루션 탐색기**에서 솔루션의 바로 가기 메뉴를 열고 **구성 관리자**를 선택합니다.  
  
  > [!NOTE]
  > **구성 관리자** 명령이 바로 가기 메뉴에 표시되지 않으면 메뉴 표시줄의 **빌드** 메뉴 아래에서 확인합니다. 여기에도 표시되지 않으면 메뉴 표시줄에서 **도구**, **옵션**을 선택하고, **옵션** 대화 상자의 왼쪽 창에서 **프로젝트 및 솔루션**, **일반**을 확장하고 나서, 오른쪽 창에서 **고급 빌드 구성 표시** 확인란을 선택합니다.  
  
   **구성 관리자** 대화 상자에서 **활성 솔루션 구성** 드롭다운 목록을 사용하여 솔루션 수준 빌드 구성을 선택하거나, 기존 구성을 수정하거나, 새 구성을 만들 수 있습니다. **활성 솔루션 플랫폼** 드롭다운 목록을 사용하여 구성의 대상으로 지정할 플랫폼을 선택하거나, 기존 플랫폼을 수정하거나, 새 플랫폼을 추가할 수 있습니다. **프로젝트 컨텍스트** 창에는 솔루션에 포함된 프로젝트가 나열됩니다. 각 프로젝트에 대해 프로젝트별 구성과 플랫폼을 선택하거나, 기존 구성과 플랫폼을 수정하거나, 새 구성 또는 플랫폼을 추가할 수 있습니다. 솔루션 수준 구성을 사용하여 솔루션을 빌드하거나 배포할 때 각 프로젝트를 포함할지 여부를 나타내는 확인란을 선택할 수도 있습니다.  
  
  원하는 구성을 설정한 후 해당 구성에 해당하는 프로젝트 속성을 설정할 수 있습니다.  
  
#### <a name="to-set-properties-based-on-configurations"></a>구성에 따라 속성을 설정하려면  
  
- **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
     **속성 페이지** 창이 열립니다.  
  
     구성에 대한 속성을 설정할 수 있습니다. 예를 들어 릴리스 구성의 경우 솔루션 빌드 시 코드가 최적화되도록 지정할 수 있고, 디버그 구성의 경우 `DEBUG` 조건부 컴파일 기호가 포함되도록 지정할 수 있습니다. 속성 페이지 설정에 대한 자세한 내용은 [프로젝트 디자이너 소개](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
## <a name="creating-and-modifying-project-configurations"></a>프로젝트 구성 만들기 및 수정  
  
#### <a name="to-create-a-project-configuration"></a>프로젝트 구성을 만들려면  
  
1. **구성 관리자** 대화 상자를 엽니다.  
  
2. **프로젝트** 열에서 프로젝트를 선택합니다.  
  
3. 해당 프로젝트의 **구성** 드롭다운 목록에서 **새로 만들기**를 선택합니다.  
  
     **새 프로젝트 구성** 대화 상자가 열립니다.  
  
4. **이름** 상자에 새 구성의 이름을 입력합니다.  
  
5. 기존 프로젝트 구성의 속성 설정을 사용하려면 **다음에서 설정 복사** 드롭다운 목록에서 구성을 선택합니다.  
  
6. 동시에 솔루션 수준 구성을 만들려면 **새 솔루션 구성 만들기** 확인란을 선택합니다.  
  
#### <a name="to-rename-a-project-configuration"></a>프로젝트 구성의 이름을 바꾸려면  
  
1. **구성 관리자** 대화 상자를 엽니다.  
  
2. **프로젝트** 열에서 이름을 바꿀 프로젝트 구성이 포함된 프로젝트를 선택합니다.  
  
3. 해당 프로젝트의 **구성** 드롭다운 목록에서 **편집**을 선택합니다.  
  
     **프로젝트 구성 편집** 대화 상자가 열립니다.  
  
4. 변경할 프로젝트 구성 이름을 선택합니다.  
  
5. **이름 바꾸기**를 선택하고 새 이름을 입력합니다.  
  
## <a name="creating-and-modifying-solution-wide-build-configurations"></a>솔루션 수준 빌드 구성 만들기 및 수정  
  
#### <a name="to-create-a-solution-wide-build-configuration"></a>솔루션 수준 빌드 구성을 만들려면  
  
1. **구성 관리자** 대화 상자를 엽니다.  
  
2. **활성 솔루션 구성** 드롭다운 목록에서 **새로 만들기**를 선택합니다.  
  
     **새 솔루션 구성** 대화 상자가 열립니다.  
  
3. **이름** 텍스트 상자에 새 구성의 이름을 입력합니다.  
  
4. 기존 솔루션 구성의 설정을 사용하려면 **다음에서 설정 복사** 드롭다운 목록에서 구성을 선택합니다.  
  
5. 동시에 프로젝트 구성을 만들려면 **새 프로젝트 구성 만들기** 확인란을 선택합니다.  
  
#### <a name="to-rename-a-solution-wide-build-configuration"></a>솔루션 수준 빌드 구성의 이름을 바꾸려면  
  
1. **구성 관리자** 대화 상자를 엽니다.  
  
2. **활성 솔루션 구성** 드롭다운 목록에서 **편집**을 선택합니다.  
  
     **솔루션 구성 편집** 대화 상자가 열립니다.  
  
3. 변경할 솔루션 구성 이름을 선택합니다.  
  
4. **이름 바꾸기**를 선택하고 새 이름을 입력합니다.  
  
#### <a name="to-modify-a-solution-wide-build-configuration"></a>솔루션 수준 빌드 구성을 수정하려면  
  
1. **구성 관리자** 대화 상자를 엽니다.  
  
2. **활성 솔루션 구성** 드롭다운 목록에서 원하는 구성을 선택합니다.  
  
3. **프로젝트 컨텍스트** 창에서 모든 프로젝트에 대해 원하는 **구성** 및 **플랫폼**을 선택하고 **빌드** 여부 및 **배포** 여부를 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](https://msdn.microsoft.com/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
