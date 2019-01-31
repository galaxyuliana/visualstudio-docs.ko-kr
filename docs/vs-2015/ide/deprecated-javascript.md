---
title: '&lt;사용 되지 않는&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b93a2b4dcc541f32c16766da0dd9dd19a4fdfe0d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759758"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;사용 되지 않는&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

사용되지 않는 함수 또는 메서드를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 선택 사항입니다. 향후 릴리스에서 함수 또는 메서드를 제거할 수는 있는지 여부 또는 여부 함수 또는 메서드를 이미 제거 및 용도 오류가 발생할 수 있는지 지정 합니다. 로 `deprecate` 릴리스에서 함수 또는 메서드를 제거할 수를 지정할 수 있습니다. 로 `remove` 함수 또는 메서드를 이미 제거 된 것을 지정 합니다.  
  
 `locid`  
 선택 사항입니다. 메서드나 함수에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
 `description`  
 선택 사항입니다. 함수 또는 메서드의 사용이 중단 되는 설명입니다.  
  
## <a name="remarks"></a>주의  
 함수를 포함 하는 주석을 추가 하는 데 필요한 요소 `<deprecated>`, 함수 본문은 문 앞에 배치 되어야 합니다. 더 이상 사용 되지 함수를 표시 하면 대체 하는 것이 좋습니다 해당 [ \<요약 >](../ide/summary-javascript.md) 사용 하 여 요소를 `<deprecated>` 요소입니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다는 `<deprecated>` 요소입니다.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
