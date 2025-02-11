---
title: '방법: 3 차원 모델에 셰이더 적용 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a55c1e71242e59c04066c09efa2375c4bafc485b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68156336"
---
# <a name="how-to-apply-a-shader-to-a-3-d-model"></a>방법: 3D 모델에 셰이더 적용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 문서에서는 모델 편집기를 사용하여 DGSL(Directed Graph Shader Language) 셰이더를 3D 모델에 적용하는 방법을 보여 줍니다.  
  
 이 문서는 다음 활동을 보여 줍니다.  
  
- 3D 모델에 셰이더 적용  
  
## <a name="applying-a-shader-to-a-3-d-model"></a>3D 모델에 셰이더 적용  
 3D 모델에 셰이더 효과를 적용하여 흥미로운 모양을 제공할 수 있습니다.  
  
 시작하기 전에 **속성** 창이 표시되는지 확인하세요.  
  
#### <a name="to-apply-a-shader-to-a-3-d-model"></a>3D 모델에 셰이더를 적용하려면  
  
1. 하나 이상의 모델이 포함된 3D 장면으로 시작합니다. 적합 한 3d 장면이 없으면 만드십시오에 설명 된 대로 [방법: 기본 3d 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)합니다. 모델에 적용할 수 있는 DGSL 셰이더가 준비되어 있어야 합니다. 적합한 셰이더가 없으면 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md) 를 저장 한 파일에 계속 있는지 확인 합니다.  
  
2. **선택** 모드에서 셰이더를 적용할 모델을 선택하고 **속성** 창에 있는 **효과** 속성 그룹의 **파일 이름** 속성에서 모델에 적용할 DGSL 셰이더를 지정합니다.  
  
   다음은 기본 색 효과가 적용된 모델입니다.  
  
   ![기본 색 효과를 보여 주는 3D 장면](../designers/media/digit-3d-model-effect.png "Digit-3D-Model-Effect")  
  
   모델에 셰이더를 적용한 후 모델을 선택하고 **속성** 창에 있는 **효과** 속성 그룹의 **(고급)** 속성에서 말줄임표( **...** ) 단추를 선택하여 셰이더 디자이너에서 모델을 열 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 기본 3d 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)   
 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md)   
 [모델 편집기](../designers/model-editor.md)   
 [셰이더 디자이너](../designers/shader-designer.md)
