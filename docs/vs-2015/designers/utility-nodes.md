---
title: 유틸리티 노드 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ff732221-b731-424c-ad5b-82ef5f21dff5
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5907b388e59b136a2d89b02348e7ac3d2b25d63c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68187520"
---
# <a name="utility-nodes"></a>유틸리티 노드
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

셰이더 디자이너에서 유틸리티 노드는 다른 범주에 명확하게 맞지 않는 일반적인 유용한 셰이더 계산을 나타냅니다. 벡터를 함께 추가하거나 결과를 조건부로 선택하는 등의 단순한 작업을 수행하는 유틸리티 노드도 있고, 널리 사용되는 조명 모델에 따라 조명의 기여도를 계산하는 등의 복잡한 작업을 수행하는 유틸리티 노드도 있습니다.  
  
## <a name="utility-node-reference"></a>유틸리티 노드 참조  
  
|노드|설명|속성|  
|----------|-------------|----------------|  
|**추가 벡터**|지정된 입력을 함께 추가하여 벡터를 만듭니다.<br /><br /> **입력:**<br /><br /> `Vector`: `float`, `float2` 또는 `float3`<br /> 입력을 추가할 값입니다.<br /><br /> `Value to Append`: `float`<br /> 추가할 값입니다.<br /><br /> **출력:**<br /><br /> `Output`: 입력 `Vector`의 유형에 따라 `float2`, `float3` 또는 `float4`<br /> 새 벡터입니다.|없음|  
|**프레스넬**|지정한 표면 법선을 기준으로 하여 프레스넬 대칭을 계산합니다.<br /><br /> 프레스넬 대칭 값은 현재 픽셀의 표면 법선이 보기 벡터와 얼마나 근접하게 일치하는지를 표현합니다. 벡터가 정렬되어 있으면 함수 결과는 0이고, 벡터의 유사성이 낮아질수록 결과 값이 커지며, 벡터가 직교 상태가 되면 결과는 최대값이 됩니다. 현재 픽셀과 카메라의 방향 간 관계에 따라 특정 효과를 보다 뚜렷하게 또는 흐리게 표시하는 데 사용할 수 있습니다.<br /><br /> **입력:**<br /><br /> `Surface Normal`: `float3`<br /> 현재 픽셀의 접선 공간에서 정의된 현재 픽셀의 표면 법선입니다. 일반 매핑에서와 같이 명확한 표면 법선을 변경하는 데 사용할 수 있습니다.<br /><br /> **출력:**<br /><br /> `Output`: `float`<br /> 현재 픽셀의 반사입니다.|**지수**<br /> 프레스넬 대칭을 계산하는 데 사용되는 지수입니다.|  
|**If**|구성 요소당 가능한 세 가지 결과 중 하나를 조건에 따라 선택합니다. 조건은 지정된 나머지 두 입력 간의 관계를 통해 정의됩니다.<br /><br /> 결과의 각 구성 요소에 대해 처음 두 입력의 해당 구성 요소 간 관계에 따라 가능한 세 결과 중 하나의 해당 구성 요소가 선택됩니다.<br /><br /> **입력:**<br /><br /> `X`: `float`, `float2`, `float3` 또는 `float4`<br /> 비교할 왼쪽 값입니다.<br /><br /> `Y`: 입력 `X`와 같은 형식<br /> 비교할 오른쪽 값입니다.<br /><br /> `X > Y`: 입력 `X`와 같은 형식<br /> `X`가 `Y`보다 크면 선택되는 값입니다.<br /><br /> `X = Y`: 입력 `X`와 같은 형식<br /> `X`가 `Y`와 같으면 선택되는 값입니다.<br /><br /> `X < Y`: 입력 `X`와 같은 형식<br /> `X`가 `Y`보다 작으면 선택되는 값입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float3`<br /> 구성 요소별로 선택된 결과입니다.|없음|  
|**램버트**|지정한 표면 법선을 사용하여 램버트 조명 모델에 따라 현재 픽셀의 색을 계산합니다.<br /><br /> 이 색은 직접 조명하에서 주변 색과 확산 조명 기여도를 합한 값입니다. 주변 색은 간접 조명의 총 기여도를 대략적으로 나타내지만, 추가 조명이 적용되지 않으므로 평면적이고 흐릿하게 표시됩니다. 확산 조명을 통해 개체에 형태와 깊이감을 줄 수 있습니다.<br /><br /> **입력:**<br /><br /> `Surface Normal`: `float3`<br /> 현재 픽셀의 접선 공간에서 정의된 현재 픽셀의 표면 법선입니다. 일반 매핑에서와 같이 명확한 표면 법선을 변경하는 데 사용할 수 있습니다.<br /><br /> `Diffuse Color`: `float3`<br /> 현재 픽셀의 확산 색으로, 보통 **점 색**입니다. 입력을 제공하지 않는 경우 기본값은 흰색입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float3`<br /> 현재 픽셀의 확산 색입니다.|없음|  
|**마스크 벡터**|지정된 벡터의 구성 요소를 마스킹합니다.<br /><br /> 색 값에서 특정 색 채널을 제거하거나, 특정 구성 요소가 후속 계산에 영향을 주지 않도록 하는 데 사용할 수 있습니다.<br /><br /> **입력:**<br /><br /> `Vector`: `float4`<br /> 마스킹할 벡터입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float4`<br /> 마스킹된 벡터입니다.|**빨간색/X**<br /> 빨강(x) 구성 요소를 마스킹하려는 경우 **False**이고, 그렇지 않으면 **True**입니다.<br /><br /> **녹색/Y**<br /> 녹색(y) 구성 요소를 마스킹하려는 경우 **False**이고, 그렇지 않으면 **True**입니다.<br /><br /> **파란색/Z**<br /> 파랑(z) 구성 요소를 마스킹하려는 경우 **False**이고, 그렇지 않으면 **True**입니다.<br /><br /> **알파/W**<br /> 알파(w) 구성 요소를 마스킹하려는 경우 **False**이고, 그렇지 않으면 **True**입니다.|  
|**리플렉션 벡터**|카메라 위치를 기준으로 접선 공간에서 현재 픽셀의 리플렉션 벡터를 계산합니다.<br /><br /> 반사, 큐브 맵 좌표 및 반사 조명 기여도를 계산하는 데 사용할 수 있습니다.<br /><br /> **입력:**<br /><br /> `Tangent Space Surface Normal`: `float3`<br /> 현재 픽셀의 접선 공간에서 정의된 현재 픽셀의 표면 법선입니다. 일반 매핑에서와 같이 명확한 표면 법선을 변경하는 데 사용할 수 있습니다.<br /><br /> **출력:**<br /><br /> `Output`: `float3`<br /> 리플렉션 벡터입니다.|없음|  
|**반사**|지정한 표면 법선을 사용하여 퐁 조명 모델에 따라 반사 조명 기여도를 계산합니다.<br /><br /> 반사 조명은 물, 플라스틱, 금속 등의 개체를 반짝이는 반사 모양으로 표시합니다.<br /><br /> **입력:**<br /><br /> `Surface Normal`: `float3`<br /> 현재 픽셀의 접선 공간에서 정의된 현재 픽셀의 표면 법선입니다. 일반 매핑에서와 같이 명확한 표면 법선을 변경하는 데 사용할 수 있습니다.<br /><br /> **출력:**<br /><br /> `Output`: `float3`<br /> 반사 하이라이트의 색 기여도입니다.|없음|
