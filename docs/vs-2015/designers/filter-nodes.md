---
title: 필터 노드 | Microsoft 문서
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f7cae2dc-e9a7-49d4-8be5-58b79868624e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 32b25b1febea59cc8ab4bc668196e60e7ccf5004
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205327"
---
# <a name="filter-nodes"></a>필터 노드
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

셰이더 디자이너에서 필터 노드는 색상 또는 질감 샘플 등의 입력을 비유적 색 값으로 변환합니다. 이러한 비유적 색 값은 일반적으로 비사실적 렌더링에서 사용되거나 다른 시각적 효과의 구성 요소로 사용됩니다.  
  
## <a name="filter-node-reference"></a>필터 노드 참조  
  
|노드|설명|속성|  
|----------|-------------|----------------|  
|**흐리게**|가우스 함수를 사용하여 질감에서 픽셀을 흐리게 합니다.<br /><br /> 이 노드를 사용하여 질감에서 색 세부 정보나 노이즈를 줄일 수 있습니다.<br /><br /> **입력:**<br /><br /> `UV`: `float2`<br /> 테스트할 텍셀의 좌표입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float4`<br /> 흐리게 표시된 색 값입니다.|**질감**<br /> 흐리게 표시 중에 사용된 샘플러와 연결된 질감 레지스터입니다.|  
|**흐리기**|지정된 색에서 색의 양을 줄입니다.<br /><br /> 색이 제거되면 색 값은 해당 회색조 값에 가까워집니다.<br /><br /> **입력:**<br /><br /> `RGB`: `float3`<br /> 채도를 낮출 색입니다.<br /><br /> `Percent`: `float`<br /> 제거할 색의 비율로, [0, 1] 범위의 정규화된 값으로 표시됩니다.<br /><br /> **출력:**<br /><br /> `Output`: `float3`<br /> 채도를 낮춘 색입니다.|**광도**<br /> 빨간색, 녹색 및 파란색 구성 요소에 지정되는 가중치입니다.|  
|**가장자리 탐지**|캐니 가장자리 검출기를 사용하여 질감에서 가장자리를 탐지합니다. 가장자리 픽셀은 흰색으로 출력되고 가장자리가 아닌 픽셀은 검은색으로 출력됩니다.<br /><br /> 추가 효과를 사용하여 가장자리 픽셀을 처리할 수 있도록 질감에서 가장자리를 식별하는 데 사용할 수 있습니다.<br /><br /> **입력:**<br /><br /> `UV`: `float2`<br /> 테스트할 텍셀의 좌표입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float4`<br /> 텍셀이 가장자리에 있으면 흰색이고, 그렇지 않으면 검은색입니다.|**질감**<br /> 가장자리 검출 중에 사용되는 샘플러와 연결된 질감 레지스터입니다.|  
|**선명하게**|질감을 선명하게 표시합니다.<br /><br /> 질감에서 세부 정보를 강조 표시하는 데 사용할 수 있습니다.<br /><br /> **입력:**<br /><br /> `UV`: `float2`<br /> 테스트할 텍셀의 좌표입니다.<br /><br /> **출력:**<br /><br /> `Output`: `float4`<br /> 흐리게 표시된 색 값입니다.|**질감**<br /> 선명하게 표시 중에 사용된 샘플러와 연결된 질감 레지스터입니다.|
