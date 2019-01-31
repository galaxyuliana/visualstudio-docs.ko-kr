---
title: '&lt;반환&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- returns JavaScript XML tag
- <returns> JavaScript XML tag
ms.assetid: 10d97829-c0ae-40a5-b04c-d8b538cdefbc
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 81a9a42a104adb2a9d9a9aba483e2588d7332868
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801778"
---
# <a name="ltreturnsgt-javascript"></a>&lt;반환&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

함수 또는 메서드 호출의 결과 대 한 문서 정보를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<returns type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    locid="descriptionID" value="code">description  
</returns>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 선택 사항입니다. 반환 값의 데이터 형식입니다. 형식에는 다음 중 하나일 수 있습니다.  
  
- ECMAScript 5 사양에는 ECMAScript 언어와 같은 입력 `Number` 고 `Object`입니다.  
  
- DOM 개체로 `HTMLElement`, `Window`, 및 `Document`합니다.  
  
- JavaScript 생성자 함수입니다.  
  
  `integer`  
  선택 사항입니다. 하는 경우 `type` 는 `Number`, 반환 값이 정수 인지 여부를 지정 합니다. 로 `true` 정수; 반환 값 임을 나타내려면이 고, 그렇지로 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `domElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `type` 특성이이 특성 보다 우선 합니다. 이 특성 문서화 된 반환 값에는 DOM 요소 인지 여부를 지정 합니다. 로 `true` 반환 값을 DOM 요소를 지정 하려면이 고, 그렇지로 `false`합니다. 경우는 `type` 특성이 설정 되지 않은 및 `domElement` 로 설정 된 `true`, IntelliSense는 문서화 된 반환 값으로 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `mayBeNull`  
  선택 사항입니다. 여부를 지정 된 문서화 된 값을 설정할 수 있습니다 null로 합니다. 로 `true` 설정에 null이 고 그렇지 않으면 반환 값을 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementType`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`,이 특성 배열의 요소 형식을 지정 합니다.  
  
  `elementInteger`  
  선택 사항입니다. 경우 `type` 는 `Array` 하 고 `elementType` 는 `Number`,이 특성은 요소 배열에서 정수 되는지 여부를 지정 합니다. 로 `true` 나타내려면 배열의 요소는가 정수인;로 고, 그렇지는 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementDomElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `elementType` 특성이이 특성 보다 우선 합니다. 하는 경우 `type` 는 `Array`,이 특성은 배열에 요소가 DOM 요소가 있는지 여부를 지정 합니다. 로 `true` 지정 하는 요소는 DOM 요소가 고, 그렇지로 `false`합니다. 경우는 `elementType` 특성이 설정 되지 않은 및 `elementDomElement` 로 설정 된 `true`, IntelliSense와 배열의 각 요소를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `elementMayBeNull`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`, 배열의 요소를 설정할 수 있는지 여부를 지정 합니다. null로 합니다. 로 `true` 설정에 null이 고 그렇지 않으면 배열의 요소를 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `locid`  
  선택 사항입니다. 반환 값에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 태그입니다.  
  
  `value`  
  선택 사항입니다. 함수 코드 자체 대신 IntelliSense에서 사용 하기 위해 평가 되어야 하는 코드를 지정 합니다. 예를 들어,와 같은 비동기 콜백에 대 한 IntelliSense를 제공 하려면이 특성을 사용할 수 있습니다는 `Promise`합니다. 사용 하는 `value` 특성과 `<returns>` 요소 긴 코드 실행을 무시 하 여 IntelliSense 성능을 향상 시킬 수 있습니다.  
  
  `description`  
  선택 사항입니다. 반환 값에 대한 설명입니다.  
  
## <a name="remarks"></a>주의  
 `<returns>` 문 앞에서 함수 본문의 요소를 배치 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `<returns>` 요소입니다.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when provided a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
// The following examples use the <remarks> element with a value attribute.  
  
function getJson(complete) {   
    /// <returns value='complete("")' ></returns>  
    var r = new XMLHttpRequest();   
    // . . .   
}   
  
getJson(function (json) {   
    json.  // IntelliSense for a String object is   
           // available here.  
});  
  
function calculate(x) {  
    /// <returns value='1'/>  
}  
calculate().  // Completion list for a Number.  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
