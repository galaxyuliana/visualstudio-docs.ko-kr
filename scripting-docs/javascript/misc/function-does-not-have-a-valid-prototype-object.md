---
title: 함수에 유효한 프로토타입 개체가 없습니다. | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31226f972ff4714dd81207cf27d862d3449184a5
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840765"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>함수에 올바른 프로토타입 개체가 없습니다.
사용 하려는 **instanceof** 개체는 특정 함수 클래스에서 파생 된 개체를 다시 정의 되지만 결정할 `prototype` 속성으로 `null`, 또는 외부 개체 형식 (모두 유효 하지 않습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체). 외부 개체 (예를 들어, Internet Explorer의 문서 또는 창 개체)에서 호스트 개체 모델에서 개체 또는 외부 COM 개체 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   함수를 확인 하십시오 `prototype` 속성은 유효한 참조 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)