---
title: 다이어그램에 배경 이미지 설정 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: e334a24c-8521-4072-b50f-e59158dde145
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 28e2358b92080bd56cfda9d395f87e5c188da221
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189398"
---
# <a name="setting-a-background-image-on-a-diagram"></a>다이어그램에 배경 이미지 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Visualization and Modeling SDK에서는 사용자 지정 코드를 사용하여 생성된 디자이너의 배경 이미지를 설정할 수 있습니다.  
  
## <a name="setting-the-background-image"></a>배경 이미지 설정  
  
#### <a name="to-set-a-background-image-for-a-generated-designer"></a>생성된 디자이너의 배경 이미지를 설정하려면  
  
1. 다이어그램 배경으로 사용할 이미지 파일을 현재 프로젝트의 Dsl\Resources 디렉터리에 복사합니다.  
  
2. **솔루션 탐색기**Dsl\Resources 폴더를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**를 클릭 하 고 **기존 항목**합니다.  
  
3. 에 **기존 항목 추가** 대화 상자에서 Dsl\Resources 폴더를 찾습니다.  
  
4. 에 **파일 형식** 목록에서 클릭 **이미지 파일**합니다.  
  
5. 디렉터리에 복사한 이미지 파일을 클릭 한 다음 클릭 **추가**합니다.  
  
6. Dsl을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성** Dsl 프로젝트의 속성을 엽니다.  
  
7. 에 **리소스** 탭을 클릭 **이 프로젝트에 기본 리소스 파일이 없습니다. 기본 리소스 파일을 만들려면 여기를 클릭하십시오.** 를 클릭합니다.  
  
8. 이미지 파일에서 그림을 드래그 하 여 리소스 파일에 추가할 **솔루션 탐색기** 리소스 창으로 합니다.  
  
9. 파일 메뉴를 열고 프로젝트 속성을 저장할 옵션을 클릭합니다.  
  
10. Dsl\Properties\Resources.resx 파일이 있으며 그 아래에 Resources.Designer.cs 파일이 있는지 확인합니다.  
  
11. Resources.Designer.cs가 없는 경우 클릭 Resources.resx 파일에서 **솔루션 탐색기**합니다.  
  
12. **속성** 창에서 `Custom Tool` 속성을 `ResXFileCodeGenerator`로 설정합니다.  
  
13. **솔루션 탐색기**Dsl 프로젝트를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**를 클릭 하 고 **새 폴더**합니다.  
  
14. 폴더의 이름을 **사용자 지정**합니다.  
  
15. 사용자 지정 폴더를 마우스 오른쪽 **추가**, 클릭 **새 항목**합니다.  
  
16. 에 **새 항목 추가** 대화 상자의 합니다 **템플릿** 목록에서 클릭 **코드 파일**.  
  
17. 에 **이름을** 상자에 입력 `BackgroundImage.cs`, 클릭 **추가**합니다.  
  
18. 네임스페이스, 다이어그램 클래스 이름 및 이미지 파일 리소스 이름을 조정하여 다음 코드를 BackgroundImage.cs 파일에 복사합니다.  
  
     "MyDiagramClass"는 Dsl\GeneratedCode\Diagrams.cs에 정의된 다이어그램 partial 클래스의 이름으로 바꿉니다. Dsl\GeneratedCode\Diagrams.cs 파일에서 정확한 네임스페이스를 검색할 수도 있습니다.  
  
    ```  
    using System;  
    using Microsoft.VisualStudio.Modeling.Diagrams;  
  
    // Fix the namespace:  
    namespace Fabrikam.MyLanguage  
    {  
      // Fix the Diagram Class name - get it from GeneratedCode\Diagram.cs  
  
      public partial class Language29Diagram  
      {  
        protected override void InitializeInstanceResources()  
        {  
          // Fix the Resources namespace and the Image resource name:  
          ImageField backgroundField = new ImageField("background",  
              Fabrikam.MyLanguage.Properties.Resources.MyPicture);  
  
          backgroundField.DefaultFocusable = false;  
          backgroundField.DefaultSelectable = false;  
          backgroundField.DefaultVisibility = true;  
          backgroundField.DefaultUnscaled = false;  
  
          shapeFields.Add(backgroundField);  
  
          backgroundField.AnchoringBehavior  
            .SetTopAnchor(AnchoringBehavior.Edge.Top, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetLeftAnchor(AnchoringBehavior.Edge.Left, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetRightAnchor(AnchoringBehavior.Edge.Right, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetBottomAnchor(AnchoringBehavior.Edge.Bottom, 0.01);  
  
          base.InitializeInstanceResources();  
        }  
      }  
    }  
    ```  
  
     프로그램 코드를 사용 하 여 모델을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [탐색 및 업데이트 프로그램 코드에서 모델](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [모양 및 연결선 정의](../modeling/defining-shapes-and-connectors.md)   
 [텍스트 및 이미지 필드 사용자 지정](../modeling/customizing-text-and-image-fields.md)   
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)
