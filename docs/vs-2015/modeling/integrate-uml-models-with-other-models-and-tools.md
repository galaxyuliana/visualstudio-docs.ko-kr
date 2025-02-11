---
title: 다른 모델 및 도구를 사용 하 여 UML 모델을 통합 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML - extending, references to models
ms.assetid: 9e75e7d1-93cf-4196-baa3-bd10b9af16d3
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1a8b67e5c784e24b1af71089d33e7db60cb1f92c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190381"
---
# <a name="integrate-uml-models-with-other-models-and-tools"></a>UML 모델을 다른 모델 및 도구와 통합
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

다른 모델 및 도메인별 언어와 UML 모델을 통합할 수 있습니다.  
  
 다양한 기능을 수행하는 확장 코드를 작성하여 다음과 같은 방식으로 모델을 통합할 수 있습니다.  
  
 다른 모델의 요소 또는 파일과 같은 다른 항목에 요소의 참조를 연결합니다.  
 UML 요소에서 ID를 문자열로 인코드하여 다른 UML 요소, 파일 또는 기타 개체에 대한 링크를 저장할 수 있습니다.  
  
 예를 들어 다른 동작 다이어그램에 UML 작업(즉, 동작 다이어그램의 요소)을 연결할 수 있는 확장을 작성할 수 있습니다. 사용자가 작업을 두 번 클릭하면 다른 다이어그램이 열립니다. 이렇게 하면 사용자가 작업의 자세한 뷰를 제공할 수 있습니다.  
  
 문자열 및 기타 데이터를 요소에 저장할 수 있는 방법에는 다음 두 가지가 있습니다.  
  
- **스테레오 타입 속성입니다.** 지정된 종류의 UML 요소에 속성을 추가하는 스테레오타입을 정의하는 UML 프로필을 정의할 수 있습니다. 예를 들어 라는 속성을 추가 하는 프로필을 정의할 수 있습니다 **MoreDetail** UML 동작 합니다. 작업에 스테레오타입을 적용한 다음 속성에 데이터를 저장하여 링크 데이터를 작업에 저장하는 확장 코드를 작성할 수 있습니다.  
  
   스테레오타입 및 해당 속성은 속성 창에서 사용자에게 표시됩니다.  
  
   이 확장을 배포하려면 프로필 정의 및 확장 코드를 단일 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 확장으로 패키징합니다.  
  
   자세한 내용은 [UML을 확장 하는 프로필 정의](../modeling/define-a-profile-to-extend-uml.md)합니다.  
  
   프로필이 메뉴 명령 및 제스처 처리기와 함께 배포 되는 샘플 프로젝트를 참조 하세요. [샘플: UML 프로필](http://go.microsoft.com/fwlink/?LinkID=213811)합니다.  
  
- **참조입니다.** 문자열 집합을 UML 요소에 연결할 수 있습니다. 파일 이름 또는 다른 요소의 GUID와 같은 정보를 저장하는 코드를 작성할 수 있습니다. 추가 정의를 제공하지 않고 이 작업을 수행할 수 있습니다. 참조는 사용자에게 직접 표시되지 않습니다.  
  
   자세한 내용은 [UML에 참조 문자열 연결 모델 요소](../modeling/attach-reference-strings-to-uml-model-elements.md)합니다. 샘플을 보려면 [다이어그램 또는 기타 파일에 UML 요소 연결](http://go.microsoft.com/fwlink/?LinkId=213813)합니다.  
  
  모델 요소에 대한 참조를 인코드하는 방법에는 다음 두 가지가 있습니다.  
  
- **GUID 및 파일 이름** 대상 모델 요소 및 포함 된 모델 또는 표시 하는 특정 다이어그램.  
  
   예를 들어 참조 [다이어그램 또는 기타 파일에 UML 요소 연결](http://go.microsoft.com/fwlink/?LinkId=213813)합니다.  
  
- **ModelBus 참조입니다.** ModelBus는 모델 간에 참조를 만들고 해결하기 위한 프레임워크입니다. 사용자가 모델의 요소를 선택할 수 있는 ModelBus 선택을 포함합니다. 또한 사용자가 대상 모델의 변경으로 인해 손실된 참조를 해결하는 데 도움이 됩니다.  
  
   자세한 내용은 [Visual Studio Modelbus를 사용 하 여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)합니다.  
  
  모델 간에 변경 내용을 전파합니다.  
  예를 들어 사용자가 하나를 변경하는 경우 다른 것도 변경되도록 요소의 이름을 연결된 다이어그램의 이름과 동기화할 수 있습니다. 이 작업을 수행하는 메커니즘에는 다음 두 가지가 있습니다.  
  
1. **VMSDK 규칙** 동일한 모델 내에서 변경 내용을 전파 하는 데 사용할 수 있습니다.  
  
    예를 들어 참조 [다이어그램 또는 기타 파일에 UML 요소 연결](http://go.microsoft.com/fwlink/?LinkId=213813)합니다.  
  
2. **VMSDK 이벤트** 예를 들어 모델 외부에 변경 내용을 전파 하는 데, 연결 된 문서의 파일 이름을 변경 하거나 다른 모델의 요소를 변경 하려면 사용할 수 있습니다.  
  
   이러한 두 메커니즘에 대 한 정보를 참조 하세요. [방법: UML 모델의 변경 내용에 응답할](../misc/how-to-respond-to-changes-in-a-uml-model.md)합니다.  
  
   요소를 끌어 모델 간에 복사  
   사용자가 항목을 UML 다이어그램으로 끌어와 요소를 만들게 할 수 있습니다. 만든 요소가 원본의 복사본일 필요는 없습니다. 예를 들어 사용자가 솔루션 탐색기에서 다른 동작 다이어그램으로 동작 다이어그램을 끌어와 새 작업을 만들게 할 수 있습니다.  
  
   자세한 내용은 참조 [모델링 다이어그램의 제스처 처리기 정의](../modeling/define-a-gesture-handler-on-a-modeling-diagram.md) 고 [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)합니다.  
  
## <a name="samples"></a>샘플  
 코드 샘플을 참조 하세요 [다이어그램 또는 기타 파일에 UML 요소 연결](http://go.microsoft.com/fwlink/?LinkId=213813)합니다. 이 샘플에서는 사용자가 파일을 UML 요소로 끌어오고 나중에 요소를 두 번 클릭하여 파일을 열 수 있습니다. 예를 들어 동작 다이어그램을 사용 사례 요소에 연결할 수 있습니다. 아이콘은 링크가 있는 요소를 표시합니다.  
  
 이 코드 샘플에서는 다음 기술을 보여 줍니다.  
  
- [UML 모델 요소에 참조 문자열 연결](../modeling/attach-reference-strings-to-uml-model-elements.md)  
  
   샘플 코드에서는 요소와 연결된 참조 문자열에 파일 경로 및 요소 GUID를 저장합니다.  
  
- UML 요소에 데코레이터를 추가하는 방법 데코레이터에 대 한 일반적인 정보를 참조 하세요 [사용자 지정 텍스트 및 이미지 필드](../modeling/customizing-text-and-image-fields.md)합니다.  
  
   샘플에서는 UML 모양에 이미지 데코레이터를 추가합니다.  
  
- [방법: UML 모델의 변경 내용에 응답](../misc/how-to-respond-to-changes-in-a-uml-model.md)  
  
   샘플에서는 다이어그램에 표시되는 새 모양에 응답하는 규칙을 정의하는 방법을 보여 줍니다.  
  
- [모델링 다이어그램의 메뉴 명령 정의](../modeling/define-a-menu-command-on-a-modeling-diagram.md)  
  
- [모델링 다이어그램의 제스처 처리기 정의](../modeling/define-a-gesture-handler-on-a-modeling-diagram.md)  
  
   샘플에서는 Windows 탐색기(또는 파일 탐색기), 솔루션 탐색기 및 기타 UML 요소에서 끌어온 항목을 처리하는 방법을 보여 줍니다.  
  
  UML 모델의 예로 DSL에서 읽을 수, 참조 [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [모델링 다이어그램의 메뉴 명령 정의](../modeling/define-a-menu-command-on-a-modeling-diagram.md)   
 [모델링 다이어그램의 제스처 처리기 정의](../modeling/define-a-gesture-handler-on-a-modeling-diagram.md)   
 [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [방법: UML 모델의 변경 내용에 응답](../misc/how-to-respond-to-changes-in-a-uml-model.md)   
 [샘플: UML 프로필](http://go.microsoft.com/fwlink/?LinkID=213811)   
 [다이어그램 또는 기타 파일에 UML 요소 연결](http://go.microsoft.com/fwlink/?LinkId=213813)
