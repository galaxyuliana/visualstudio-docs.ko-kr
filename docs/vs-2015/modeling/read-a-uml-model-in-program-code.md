---
title: 프로그램 코드에서 UML 모델 읽기 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML API, reading models
ms.assetid: 0f63105e-6079-498a-94f1-318c0f5f9621
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 37539ee6c031d88b9db279cc61214ac5e3077e76
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63387676"
---
# <a name="read-a-uml-model-in-program-code"></a>프로그램 코드에서 UML 모델 읽기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

UML API를 사용하여 UML 모델 및 해당 다이어그램을 로드할 수 있습니다.  
  
## <a name="Reading"></a> 프로그램 코드에서 모델 읽기  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 창에 표시하지 않고 모델의 콘텐츠에 액세스하려면 `ModelingProject.LoadReadOnly()`를 사용합니다.  
  
 예를 들어:  
  
```  
using Microsoft.VisualStudio.Uml.Classes;   
               // for IElement  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility;   
               // for ModelingProject  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;  
               // for IModelStore  
...   
string projectPath = @"C:\MyProjectFolder\MyProject.modelproj";  
using (IModelingProjectReader projectReader =  
           ModelingProject.LoadReadOnly(projectPath))  
{  
   IModelStore store = projectReader.Store;  
   foreach (IClass umlClass in store.AllInstances<IClass>())  
   {   
       ...  
   }  
}  
```  
  
 다이어그램에서 모양을 읽으려는 경우 프로젝트를 읽은 후 다이어그램을 읽어야 합니다.  
  
 예를 들어:  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;   
                             // for IDiagram  
...  
foreach (string diagramFile in projectReader. DiagramFileNames)  
{   
  IDiagram diagram = projectReader.LoadDiagram(diagramFile);  
  foreach (IShape<IElement> shape   
         in diagram.GetChildShapes<IElement>())  
  { ... }  
}  
```  
  
## <a name="alternative-methods"></a>대체 방법  
 대부분의 응용 프로그램에 대 한 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Modelbus 참조 모델 및 요소 내에 더 강력 하 고이 항목에서 설명 하는 메서드를 사용 하 여 보다 유연 하 게 할 수 있습니다. Modelbus는 동일한 모델이나 다른 모델의 임의 요소 간에 링크를 만드는 표준 방법을 제공합니다. 자세한 내용은 [다른 모델 및 도구를 사용 하 여 통합 UML 모델](../modeling/integrate-uml-models-with-other-models-and-tools.md)합니다.  
  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] API를 사용하여 사용자 인터페이스에서 모델 및 다이어그램을 열 수도 있습니다. 자세한 내용은 [Visual Studio API를 사용 하 여 UML 모델 열기](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md)합니다.  
  
## <a name="Standalone"></a> 독립 실행형 응용 프로그램  
 이전 섹션의 예제는 Visual Studio 확장에서 작동합니다. 독립 실행형 애플리케이션에서 모델을 읽을 수 있지만 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로젝트에 일부 참조를 추가해야 합니다.  
  
> [!NOTE]
> 독립 실행형 애플리케이션에서 모델을 읽는 방법의 세부 정보는 이후 버전의 제품에서 변경될 수 있습니다. 현재 버전에서 액세스할 수 있는 일부 기능을 이후 버전에서는 사용하지 못할 수도 있습니다.  
  
#### <a name="to-add-references-to-read-a-model-in-a-stand-alone-application"></a>독립 실행형 애플리케이션에서 모델을 읽기 위해 참조를 추가하려면  
  
1. 솔루션 탐색기에서 응용 프로그램을 작성 하는 지정 하 고 클릭 한 다음 프로젝트를 마우스 오른쪽 단추로 **속성**합니다. 속성 편집기에서에 **응용 프로그램** 탭에서 **대상 프레임 워크** .NET Framework의 필수 버전으로 합니다.  
  
2. UML 모델에 액세스하는 데 필요한 [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] 참조를 추가합니다. 일반적으로 다음과 같습니다.  
  
   - Microsoft.VisualStudio.Uml.Interfaces.dll  
  
   - Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll  
  
3. 이전 섹션에 나열 된 참조 외에도 다음 프로젝트 참조를 추가할 **\Program Files\Microsoft Visual Studio [version] \Common7\IDE\PrivateAssemblies**:  
  
   - Microsoft.VisualStudio.Uml.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.ModelStore.Dsl.dll  
  
     애플리케이션에서 다이어그램을 읽으려는 경우 다음 참조가 필요할 수도 있습니다.  
  
   - Microsoft.VisualStudio.TeamArchitect.ActivityDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.ComponentDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.LogicalClassDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.SequenceDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.UseCase.Dsl.dll  
  
## <a name="see-also"></a>참고 항목  
 [UML API를 사용한 프로그래밍](../modeling/programming-with-the-uml-api.md)   
 [UML 모델 및 다이어그램 확장](../modeling/extend-uml-models-and-diagrams.md)
