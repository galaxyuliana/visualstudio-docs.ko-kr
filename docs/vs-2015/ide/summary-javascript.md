---
title: '&lt;요약&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 81d41918d61bbe95cfe19d2382535449a47deb8c
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54775816"
---
# <a name="ltsummarygt-javascript"></a>&lt;요약&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

함수 또는 메서드에 대한 설명을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `locid`  
 선택 사항입니다. 메서드나 함수에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
 `description`  
 선택 사항입니다. 함수 또는 메서드의 설명입니다.  
  
## <a name="remarks"></a>주의  
 함수를 포함 하는 주석을 추가 하는 데 필요한 요소 [ \<요약 >](../ide/summary-javascript.md)합니다 [ \<param >](../ide/param-javascript.md), 및 [ \<반환 >](../ide/returns-javascript.md), 함수 본문은 문 앞에 배치 되어야 합니다.  
  
## <a name="example"></a>예  
 다음 코드를 사용 하는 방법을 보여 줍니다는 `<summary>` 요소입니다.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
