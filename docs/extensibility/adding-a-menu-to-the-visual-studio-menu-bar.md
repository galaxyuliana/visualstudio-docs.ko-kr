---
title: Visual Studio 메뉴 모음에 메뉴 추가 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b4201e6c09037259888290312c4dce616f77459
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54988313"
---
# <a name="add-a-menu-to-the-visual-studio-menu-bar"></a>Visual Studio 메뉴 모음에 메뉴 추가
이 연습에서는 Visual Studio 통합된 개발 환경 (IDE)의 메뉴 모음에 메뉴를 추가 하는 방법을 보여 줍니다. IDE 메뉴 모음에 메뉴 범주와 같은 **파일**를 **편집**를 **뷰**를 **창**, 및 **도움말** .  
  
 Visual Studio 메뉴 모음에 새 메뉴에 추가 하기 전에 기존 메뉴 내에서 명령을 배치 해야 하는지 여부를 하는 것이 좋습니다. 명령 배치에 대 한 자세한 내용은 참조 하세요. [Visual Studio의 메뉴 및 명령](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)입니다.  
  
 메뉴에서 선언 되는 *.vsct* 프로젝트의 파일입니다. 메뉴에 대 한 자세한 내용은 및 *.vsct* 파일을 참조 하십시오 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
 이 연습을 완료 하면 라는 메뉴를 만들 수 있습니다 **TestMenu** 명령을 포함 하는 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015부터 수행 설치 하면 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="create-a-vsix-project-that-has-a-custom-command-item-template"></a>사용자 지정 명령 항목 템플릿을 VSIX 프로젝트를 만듭니다  
  
1.  라는 VSIX 프로젝트를 만듭니다 `TopLevelMenu`합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다 합니다 **새 프로젝트** 대화 상자의 **Visual C#** / **확장성**합니다.  자세한 내용은 [메뉴 명령을 사용 하 여 확장 프로그램을 만들려면](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  프로젝트를 열면 라는 사용자 지정 명령 항목 템플릿을 추가 **TestCommand**합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택한 **사용자 지정 명령**입니다. 에 **이름을** 창의 맨 아래에 있는 필드에 명령 파일 이름을 *TestCommand.cs*합니다.  
  
## <a name="create-a-menu-on-the-ide-menu-bar"></a>IDE 메뉴 모음의 메뉴 만들기  
  
1. **솔루션 탐색기**오픈 *TestCommandPackage.vsct*합니다.  
  
    파일 끝에는 \<기호 > 몇 가지를 포함 하는 노드 \<GuidSymbol > 노드. GuidTestCommandPackageCmdSet 노드에서 새 기호를 다음과 같이 추가 합니다.  
  
   ```xml  
   <IDSymbol name="TopLevelMenu" value="0x1021"/>  
   ```  
  
2. 빈 \<메뉴 >에서 노드를 \<명령 > 노드를 직전 \<그룹 >입니다. 에 \<메뉴 > 노드를 추가 \<메뉴 > 다음과 같은 노드:  
  
   ```xml  
   <Menus>  
         <Menu guid="guidTestCommandPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">  
           <Parent guid="guidSHLMainMenu"  
                   id="IDG_VS_MM_TOOLSADDINS" />  
           <Strings>  
             <ButtonText>TestMenu</ButtonText>  
             <CommandName>TestMenu</CommandName>  
           </Strings>  
       </Menu>  
   </Menus>  
   ```  
  
    합니다 `guid` 고 `id` 명령 집합의 명령 집합 및 특정 메뉴를 지정 하는 메뉴의 값입니다.  
  
    합니다 `guid` 고 `id` 부모 값의 도구 및 추가 기능 메뉴를 포함 하는 Visual Studio 메뉴 모음 섹션에는 메뉴의 위치입니다.  
  
    값을 `CommandName` 문자열 텍스트를 메뉴 항목에 표시 되도록 지정 합니다.  
  
3. 에 \<그룹 > 섹션을 찾습니다 합니다 \<그룹 > 변경를 \<부모 > 방금 추가한 메뉴를 가리키도록 요소:  
  
   ```csharp  
   <Groups>  
         <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
           <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
         </Group>  
       </Groups>  
   ```  
  
    이렇게 하면 새 메뉴 그룹 부분입니다.  
  
4. 찾기는 `Buttons` 섹션입니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 템플릿은 생성에 `Button` 로 설정 하는 부모 요소 `MyMenuGroup`합니다. 결과적으로,이 명령을 메뉴에 표시 됩니다.  
  
## <a name="build-and-test-the-extension"></a>빌드 및 확장 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스의 인스턴스 표시 됩니다.  
  
2.  실험적 인스턴스에서 메뉴 모음에 포함 되어야 합니다는 **TestMenu** 메뉴.  
  
3.  에 **TestMenu** 메뉴에서 클릭 **테스트 명령 호출**합니다.  
  
     메시지 상자를 표시 하 고 "TestCommand 패키지 내에서 TopLevelMenu.TestCommand.MenuItemCallback()" 메시지를 표시 해야 합니다. 이 새 명령이 작동 하는 것을 나타냅니다.  
  
## <a name="see-also"></a>참고자료  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)