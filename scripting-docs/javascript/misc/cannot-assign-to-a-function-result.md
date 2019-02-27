---
title: 함수 결과에 할당할 수 없습니다. | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5003
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38cf04b388eaea8ad85f0399978f914feb937c0a
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844015"
---
# <a name="cannot-assign-to-a-function-result"></a>함수 결과에 할당할 수 없습니다.
함수 결과에 값을 할당 하려고 했습니다. 함수의 결과 변수에 할당할 수 있지만 변수로 사용할 수 없습니다. 함수 자체에 새 값을 할당 하려는 경우 (함수 호출 연산자) 괄호를 생략 합니다. 다음 예제에서는이 오류가 생성 되는 상황을 보여 줍니다.  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   함수 호출 결과의 값을 넣지 마십시오 *할당할*합니다. 함수 호출의 결과 할당할 수 있습니다 *변수로* 있지만.  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
-   또는 변수에 함수 자체 (및 해당 반환 값이 아닌) 할당할 수 있습니다.  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [JavaScript 코드 작성](../../javascript/writing-javascript-code.md)   
 [함수](../../javascript/functions-javascript.md)