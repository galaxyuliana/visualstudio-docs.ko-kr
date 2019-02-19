---
title: '&lt;필드&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <field> JavaScript XML tag
- field JavaScript XML tag
ms.assetid: c494bae0-3095-42a3-aa0a-4c415188c65c
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b2fe09070261460b7b83f54de44a07cf96d40cf2
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54766558"
---
# <a name="ltfieldgt-javascript"></a>&lt;필드&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

필드 또는 개체에 정의 된 멤버에 대 한 설명을 등의 문서 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<field name="fieldName" static="true|false"  
    type="FieldType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    helpKeyword="keyword" locid="descriptionID"  
    value="code">description  
</field>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 필드 또는 멤버의 이름입니다. 경우는 `<field>` 요소를 사용 하는 생성자 함수에서 `name` 필요 하 고 태그를 적용할 멤버를 정의 합니다. 경우는 `<field>` 요소는 직접 필드,이 특성은 무시에 주석을 달고 Visual Studio에서 사용 하는 이름은 소스 코드에서 실제 필드의 이름입니다.  
  
 `static`  
 선택 사항입니다. 필드는 생성자 함수 멤버인 생성자 함수에서 반환 된 개체의 멤버 지정 합니다. 로 `true` 생성자 함수의 구성원으로 필드를 처리 합니다. 로 `false` 생성자 함수에서 반환 되는 개체의 구성원으로 필드를 처리 합니다.  
  
 `type`  
 선택 사항입니다. 필드의 데이터 형식입니다. 형식에는 다음 중 하나일 수 있습니다.  
  
- ECMAScript 5 사양에는 ECMAScript 언어와 같은 입력 `Number` 고 `Object`입니다.  
  
- DOM 개체로 `HTMLElement`, `Window`, 및 `Document`합니다.  
  
- JavaScript 생성자 함수입니다.  
  
  `integer`  
  선택 사항입니다. 하는 경우 `type` 는 `Number`, 필드는 정수 인지 여부를 지정 합니다. 로 `true` 필드는 정수; 임을 나타내려면이 고, 그렇지로 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `domElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `type` 특성이이 특성 보다 우선 합니다. 이 특성은 문서화 된 필드는 DOM 요소 인지 여부를 지정 합니다. 로 `true` 필드는 DOM 요소를 지정 하려면이 고, 그렇지로 `false`합니다. 경우는 `type` 특성이 설정 되지 않은 및 `domElement` 로 설정 된 `true`, IntelliSense를 문서화 된 필드를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `mayBeNull`  
  선택 사항입니다. 문서화 된 필드를 설정할 수 있는지 여부를 지정 하려면 null입니다. 로 `true` 로 필드에 null이 고 그렇지 않으면 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementType`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`,이 특성 배열의 요소 형식을 지정 합니다.  
  
  `elementInteger`  
  선택 사항입니다. 경우 `type` 는 `Array` 하 고 `elementType` 는 `Number`,이 특성은 요소 배열에서 정수 되는지 여부를 지정 합니다. 로 `true` 나타내려면 배열의 요소는가 정수인;로 고, 그렇지는 `false`합니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `elementDomElement`  
  선택 사항입니다. 이 특성은 사용 되지 않습니다. `elementType` 특성이이 특성 보다 우선 합니다. 하는 경우 `type` 는 `Array`,이 특성은 배열에 요소가 DOM 요소가 있는지 여부를 지정 합니다. 로 `true` 지정 하는 요소는 DOM 요소가 고, 그렇지로 `false`합니다. 경우는 `elementType` 특성이 설정 되지 않은 및 `elementDomElement` 로 설정 된 `true`, IntelliSense와 배열의 각 요소를 처리는 `HTMLElement` 문 완성 기능을 수행 하는 경우.  
  
  `elementMayBeNull`  
  선택 사항입니다. 하는 경우 `type` 는 `Array`, 배열의 요소를 설정할 수 있는지 여부를 지정 합니다. null로 합니다. 로 `true` 설정에 null이 고 그렇지 않으면 배열의 요소를 설정할 수 있도록 나타내려면 `false`합니다. 기본값은 `false`입니다. IntelliSense 정보를 제공 하도록 Visual Studio에서이 특성을 사용 되지 않습니다.  
  
  `helpKeyword`  
  선택 사항입니다. 에 대 한 F1 도움말 키워드입니다.  
  
  `locid`  
  선택 사항입니다. 필드에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 태그입니다.  
  
  `value`  
  선택 사항입니다. 함수 코드 자체 대신 IntelliSense에서 사용 하기 위해 평가 되어야 하는 코드를 지정 합니다. 에 대 한 `<field>`,이 특성 생성자 함수에 대 한 지원 되지만 개체 리터럴에 대 한 지원 되지 않습니다. 이 사용 하 여 특성 필드 형식이 정의 된 형식 정보를 제공 하는 것입니다. 예를 들어 사용할 수 있습니다 `value=’1’` 필드 형식을 숫자로 처리 하도록 합니다.  
  
  `description`  
  선택 사항입니다. 필드에 대 한 설명입니다.  
  
## <a name="remarks"></a>주의  
 `name` 특성은 생성자 함수에서 필드를 문서화 하는 경우에 필요 합니다. 다른 모든 시나리오에 대 한 모든 특성이 `<field>` 요소는 선택 사항입니다.  
  
 생성자 함수를 문서화 하는 경우는 `<field>` 요소 필드 선언 바로 앞에 나타나야 합니다. `name` 특성에는 소스 코드에 사용 되는 필드 이름과 일치 해야 합니다. 개체 멤버에 대 한 합니다 `name` 경우 특성을 생략할 수 있습니다는 `<field>` 개체 멤버 선언 직전 요소가 표시 됩니다.  
  
## <a name="example"></a>예  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `<field>` 요소입니다.  
  
```javascript  
// Use of <field> in an object definition.  
var Rectangle = {  
    /// <field type='Number'>The width of the rectangle.</field>  
    wid: 5,  
    /// <field type='Number'>The length of the rectangle.</field>  
    len: 0,  
    /// <field type='Number'>Returns the area of the rectangle.</field>  
    getArea: function (wid, len) {  
        return len * wid;  
    }  
}  
  
// Use of <field> in a constructor function.  
// The name attribute is required.  
function Engine() {  
    /// <field name='HorsePower' type='Number'>The engine's horsepower.</field>  
    this.HorsePower = 150;  
}  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<field>` 요소를 `static` 특성이로 설정 `true`합니다.  
  
```javascript  
function Engine() {  
    /// <field name='HorsePower' static='true' type='Number'>static field desc.</field>  
}  
  
Engine.HorsePower = 140;  
// IntelliSense on the field is available here.  
Engine.  
  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<field>` 요소를 `static` 특성이로 설정 `false`합니다.  
  
```javascript  
function Engine() {  
    /// <field name='HorsePower' static='false' type='Number'>Non-static field desc.</field>  
}  
  
Engine.HorsePower = 140;  
var eng = new Engine();  
// IntelliSense on the field is available here.  
eng.  
  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<field>` 요소는 `value` 특성입니다.  
  
```javascript  
function calculator(a) {  
    /// <field name='f' value='1'/>  
}  
new calculator().f.   // Completion list for a Number.  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)
