---
title: 예상 '@' | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05842c274c27165a7065cb90fda60dd75da2a659
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840340"
---
# <a name="expected-"></a>'@'가 필요합니다.
사용 하 여 조건부 컴파일 문에서 사용할 변수를 만들려고 합니다 `@set` 문을 배치 하지 않고 있지만 at 기호 "**@**" 변수 이름 앞입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   추가 at 기호 "**@**" 변수 이름 바로 앞입니다. 예를 들어:  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [@set Statement](../../javascript/reference/at-set-statement-javascript.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)