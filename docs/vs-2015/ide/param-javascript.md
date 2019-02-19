---
title: '&lt;param&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <param> JavaScript XML tag
- param JavaScript XML tag
ms.assetid: 2c4e0167-c1dd-4e54-83f1-c437856bddc1
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a8477de8bf84950d778d4ce843522be35b2d7387
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54772383"
---
# <a name="ltparamgt-javascript"></a>&lt;param&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

함수 또는 메서드 매개 변수에 대해 문서 정보를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<param name="parameterName" type="ParameterType"  
    integer="true|false" domElement="true|false"  
    mayBeNull="true|false" elementType="ArrayElementType"  
    elementInteger="true|false" elementDomElement="true|false"  
    elementMayBeNull="true|false" locid="descriptionID"  
    parameterArray="true|false" optional="true|false"  
    value="code">description  
</param>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 필수 요소. 매개 변수의 이름입니다.  
  
 `type`  
 선택 사항입니다. 매개 변수의 데이터 형식입니다. 형식에는 다음 중 하나일 수 있습니다.  
  
- ECMAScript 5 사양에는 ECMAScript 언어와 같은 입력 `Number` 고 `Object`입니다.  
  
- DOM 개체로 `HTMLElement`, `Window`, 및 `Document`합니다.  
  
- JavaScript 생성자 함수입니다.  
  
  `integer`  
  선택 사항입니다. 하는 경우 `type` 는 `Number`, 매개 변수는 정수 인지 여부를 지정 합니다. 로 `true` 매개 변수는 정수; 임을 나타내려면이 고, 그렇지로 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `domElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `type` 특성이이 특성 보다 우선 합니다. 이 특성은 문서화 된 매개 변수는 DOM 요소 인지 여부를 지정 합니다. 로 `true` 매개 변수는 DOM 요소를 지정 하려면이 고, 그렇지로 `false`합니다. 경우는 `type` 특성이 설정 되지 않은 및 `domElement` 로 설정 된 `true`, IntelliSense를 문서화 된 매개 변수를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `mayBeNull`  
  선택 사항입니다. 문서화 된 매개 변수를 설정할 수 있는지 여부를 지정 하려면 null입니다. 로 `true` 설정에 null이 고 그렇지 않으면 매개 변수를 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementType`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`,이 특성 배열의 요소 형식을 지정 합니다.  
  
  `elementInteger`  
  선택 사항입니다. 경우 `type` 는 `Array` 하 고 `elementType` 는 `Number`,이 특성은 요소 배열에서 정수 되는지 여부를 지정 합니다. 로 `true` 나타내려면 배열의 요소는가 정수인;로 고, 그렇지는 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementDomElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `elementType` 특성이이 특성 보다 우선 합니다. 하는 경우 `type` 는 `Array`,이 특성은 배열에 요소가 DOM 요소가 있는지 여부를 지정 합니다. 로 `true` 지정 하는 요소는 DOM 요소가 고, 그렇지로 `false`합니다. 경우는 `elementType` 특성이 설정 되지 않은 및 `elementDomElement` 로 설정 된 `true`, IntelliSense와 배열의 각 요소를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `elementMayBeNull`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`, 배열의 요소를 설정할 수 있는지 여부를 지정 합니다. null로 합니다. 로 `true` 설정에 null이 고 그렇지 않으면 배열의 요소를 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `locid`  
  선택 사항입니다. 매개 변수에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
  `parameterArray`  
  선택 사항입니다. 문서화 된 매개 변수에서 지원 되는 매개 변수를 반복에 비슷한 함수 호출에서 반복 될 수 있는지 여부를 지정 된 `String.format` 함수입니다. 로 `true` 로 매개 변수가 고 그렇지 않으면 반복 수 있음을 나타내려면 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `optional`  
  선택 사항입니다. 문서화 된 매개 변수는 함수 호출에서 선택적 여부를 지정 합니다. 로 `true` 로 매개 변수가 고 그렇지 않으면 선택적 임을 나타내려면 `false`합니다.  
  
  `value`  
  선택 사항입니다. 함수 코드 자체 대신 IntelliSense에서 사용 하기 위해 평가 되어야 하는 코드를 지정 합니다. 이 사용 하 여 특성 매개 변수 형식이 정의 된 형식 정보를 제공 하는 것입니다. 예를 들어 사용할 수 있습니다 `value=’1’` 매개 변수 형식을 숫자로 처리 하도록 합니다.  
  
  `description`  
  선택 사항입니다. 매개 변수의 설명입니다.  
  
## <a name="remarks"></a>주의  
 유일한 필수 특성은 `name`합니다. 다른 모든 특성은 선택 사항입니다.  
  
 요소와 같은 함수에 주석을 추가 하는 데 [ \<요약 >](../ide/summary-javascript.md)를 [ \<param >](../ide/param-javascript.md), 및 [ \<반환 >](../ide/returns-javascript.md)를 배치 해야 합니다 모든 문 앞 함수 본문입니다.  
  
 여러 개의 `<param>` 중 하나는 동일한 이름을 가진 요소를 `<param>` 요소에서 사용 되 고 중복 요소는 무시 됩니다. 요소는 결정 하는 동작을 정의 되지 않았습니다. 경우 `name` 참조 존재 하지 않는 매개 변수에 요소가 무시 됩니다.  
  
## <a name="example"></a>예  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `<param>` 요소입니다.  
  
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
  
// Uses of <param> with the value attribute.  
  
function calculate(a) {  
    /// <param name='a' value='1'/>  
    a.    // Completion list for a Number.  
}  
  
function calculate(a) {  
    /// <param name='a' value='{x:0,y:0}'/>  
    a.    // x and y appear in the completion list.  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
