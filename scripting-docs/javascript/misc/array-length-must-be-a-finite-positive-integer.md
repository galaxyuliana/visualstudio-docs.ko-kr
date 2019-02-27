---
title: 배열 길이 유한한 양의 정수 여야 합니다. | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 691f7aff61a8a2bfae6444540afe9a28a200278d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840434"
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>배열 길이는 유한 양의 정수여야 합니다.
호출 하는 **배열** 생성자 인수를 정수 (0 + 양의 정수 집합의 정수 구성)를 사용 하 여 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   양의 정수를 사용 하 여 새로 만들 때에 `Array` 개체입니다. 정수가 아닌 단일 요소가 있는 배열의 만들려는 경우에 두 단계로 수행 합니다. 먼저 하나의 요소만 포함 된 배열을 만든 다음 (array[0]) 첫 번째 요소 값을 저장. 다음은이 오류를 생성 하는 예제입니다.  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     다음 예제에서는 단일 숫자 요소를 사용 하 여 배열을 지정 하는 올바른 방법을 보여 줍니다.  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     최대 정수 값 (약 4 십억)이 아닌 배열의 크기에 대 한 상한 제한은 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)