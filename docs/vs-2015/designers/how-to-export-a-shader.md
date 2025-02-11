---
title: '방법: 셰이더 내보내기 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 74b3fa73c3a67c721b9311a964e26fa9ab48c16e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176489"
---
# <a name="how-to-export-a-shader"></a>방법: 셰이더 내보내기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 문서에서는 앱에서 사용할 수 있도록 셰이더 디자이너를 사용하여 DGSL(Directed Graph Shader Language) 셰이더를 내보내는 방법을 보여 줍니다.  
  
 이 문서는 다음 활동을 보여 줍니다.  
  
- 셰이더 내보내기  
  
## <a name="exporting-a-shader"></a>셰이더 내보내기  
 셰이더 디자이너를 사용하여 셰이더를 만든 후, 앱에서 사용하기 전에 그래픽 API가 이해하는 형식으로 셰이더를 내보내야 합니다. 요구 사항에 따라 다양한 방법으로 셰이더를 내보낼 수 있습니다.  
  
#### <a name="to-export-a-shader"></a>셰이더를 내보내려면  
  
1. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 **시각적 셰이더 그래프(.dgsl)** 파일을 엽니다.  
  
     열 수 있는 **시각적 셰이더 그래프(.dgsl)** 파일이 없으면 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md)합니다.  
  
2. **셰이더 디자이너** 도구 모음에서 **고급**, **내보내기**, **다른 이름으로 내보내기**를 선택합니다. **셰이더 내보내기** 대화 상자가 표시됩니다.  
  
3. **파일 형식** 드롭다운 목록에서 내보내려는 형식을 선택합니다.  
  
     선택할 수 있는 형식은 다음과 같습니다.  
  
     **HLSL 픽셀 셰이더(\*.hlsl)**  
     셰이더를 HLSL(High Level Shader Language) 소스 코드로 내보냅니다. 이 옵션을 사용하면 앱에 배포된 후더라도 나중에 셰이더를 수정할 수 있습니다. 이렇게 하면 최종 사용자 문제에 따라 코드를 더 쉽게 디버그 및 패치할 수 있지만, 예를 들어 사용자가 경쟁 게임에서 부당한 이득을 얻기 위해 바람직하지 않은 방법으로 셰이더를 수정하기도 더 쉽습니다. 셰이더의 로드 시간이 늘어날 수도 있습니다.  
  
     **컴파일된 픽셀 셰이더(\*.cso)**  
     셰이더를 HLSL 바이트 코드로 내보냅니다. 이 옵션을 사용하면 앱에 배포된 후더라도 나중에 셰이더를 수정할 수 있습니다. 이렇게 하면 최종 사용자 문제에 따라 코드를 더 쉽게 디버그 및 패치할 수 있지만, 셰이더가 미리 컴파일되므로 앱이 셰이더를 로드할 때 추가적인 런타임 오버헤드가 발생하지 않습니다. 그래도 충분히 숙련된 사용자가 바람직하지 않은 방법으로 셰이더를 수정할 수 있지만 셰이더를 컴파일하면 이런 수정이 훨씬 더 어려워집니다.  
  
     **C++ 헤더(\*.h)**  
     HLSL 바이트 코드가 포함된 바이트 배열을 정의하는 C 스타일 헤더로 셰이더를 내보냅니다. 이 옵션을 사용하면 수정 사항을 테스트하기 위해 앱을 다시 컴파일해야 하므로 최종 사용자 문제에 따라 코드를 디버그 및 패치하는 데 더 많은 시간이 사용될 수 있습니다. 그러나 이 옵션을 사용하면 앱에 배포된 후 셰이더를 수정하기가 어려울 수 있지만 바람직하지 않은 방법으로 셰이더를 수정하려는 사용자가 가장 힘들 것입니다.  
  
4. **파일 이름** 콤보 상자에서 내보낸 셰이더의 이름을 지정하고 **저장** 단추를 선택합니다.  
  
## <a name="see-also"></a>관련 항목  
 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md)   
 [셰이더 디자이너](../designers/shader-designer.md)
