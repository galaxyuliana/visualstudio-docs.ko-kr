---
title: 조건부 컴파일이 해제 되었습니다 | Microsoft 문서
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d3c225df20113308ee7037742ad74efb6a0cc2e
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840356"
---
# <a name="conditional-compilation-is-turned-off"></a>조건부 컴파일이 해제되었습니다.
첫 번째 설정 조건부 컴파일 없이 조건부 컴파일 변수를 사용 하려고 했습니다. 조건부 컴파일 설정 지시를 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] @ 조건부 컴파일 변수로 시작 하는 식별자를 해석 하는 컴파일러입니다. 문 사용 하 여 조건부 코드를 시작 하 여이 수행 합니다.  
  
```js
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   조건부 코드의 시작 부분에 다음 문을 추가 합니다.  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on Statement](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if Statement](../../javascript/reference/at-if-statement-javascript.md)   
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)