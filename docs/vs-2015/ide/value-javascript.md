---
title: '&lt;값&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <value> JavaScript XML tag
- value JavaScript XML tag
ms.assetid: 983e31de-cb1d-411e-b60d-eea6698a26f6
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ac74dde41a2d6cea0a768cfc89838cc34ce41afd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54799144"
---
# <a name="ltvaluegt-javascript"></a>&lt;값&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

에 대 한 설명서 정보 지정 `get` 및 `set` ECMAScript 3 속성에 대 한 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
<value type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    locid="descriptionID">description  
</value>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 선택 사항입니다. 속성의 데이터 형식입니다. 형식에는 다음 중 하나일 수 있습니다.  
  
- ECMAScript 5 사양에는 하는 ECMAScript 언어 형식 `Number` 고 `Object`입니다.  
  
- DOM 개체로 `HTMLElement`, `Window`, 및 `Document`합니다.  
  
- JavaScript 생성자 함수입니다.  
  
  `integer`  
  선택 사항입니다. 하는 경우 `type` 는 `Number`, 속성 정수 인지 여부를 지정 합니다. 로 `true` 속성이 정수; 임을 나타내려면이 고, 그렇지로 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `domElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `type` 특성이이 특성 보다 우선 합니다. 이 특성 문서화 된 속성에는 DOM 요소 인지 여부를 지정 합니다. 로 `true` DOM 요소를; 속성을 지정 하려면이 고, 그렇지로 `false`합니다. 경우는 `type` 특성이 설정 되지 않은 및 `domElement` 로 설정 된 `true`, IntelliSense를 문서화 된 속성을 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `mayBeNull`  
  선택 사항입니다. 문서화 된 속성을 설정할 수 있는지 여부를 지정 하려면 null입니다. 로 `true` 설정에 null이 고 그렇지 않으면 속성을 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementType`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`,이 특성 배열의 요소 형식을 지정 합니다.  
  
  `elementInteger`  
  선택 사항입니다. 경우 `type` 는 `Array` 하 고 `elementType` 는 `Number`,이 특성은 요소 배열에서 정수 되는지 여부를 지정 합니다. 로 `true` 나타내려면 배열의 요소는가 정수인;로 고, 그렇지는 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementDomElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `elementType` 특성이이 특성 보다 우선 합니다. 하는 경우 `type` 는 `Array`,이 특성은 배열에 요소가 DOM 요소가 있는지 여부를 지정 합니다. 로 `true` 지정 하는 요소는 DOM 요소가 고, 그렇지로 `false`합니다. 경우는 `elementType` 특성이 설정 되지 않은 및 `elementDomElement` 로 설정 된 `true`, IntelliSense와 배열의 각 요소를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `elementMayBeNull`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`, 배열의 요소를 설정할 수 있는지 여부를 지정 합니다. null로 합니다. 로 `true` 설정에 null이 고 그렇지 않으면 배열의 요소를 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `locid`  
  선택 사항입니다. 속성에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
  `description`  
  선택 사항입니다. 속성의 설명입니다.  
  
## <a name="remarks"></a>주의  
 ECMAScript 5 속성 사용 합니다 [ \<요약 >](../ide/summary-javascript.md) 요소입니다.  
  
 사용 합니다 `<value>` 요소 바로 앞의 `get` 또는 `set` 함수입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다 합니다 `<value>` 요소는 `get` 함수입니다.  
  
```javascript  
function Sys$CancelEventArgs$get_cancel() {  
    /// <value type="Boolean" locid="P:J#Sys.CancelEventArgs.cancel"></value>  
    if (arguments.length !== 0) throw Error.parameterCount();  
    return this._cancel();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
