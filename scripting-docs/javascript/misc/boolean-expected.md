---
title: 부울이 필요 | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82123fe2a38b3de1d6e6c015f47bc5f7edd02791
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840526"
---
# <a name="boolean-expected"></a>부울이 필요합니다.
호출 하려고 합니다 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 이외의 다른 형식의 개체의 메서드를 `Boolean`입니다. 이 형식의 호출 개체 유형 이어야 `Boolean`합니다. 예를 들어:

```JavaScript
var o = new Object;
o.f = Boolean.prototype.toString;
o.f();
```

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 만 호출 합니다 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 형식의 개체에 있는 메서드의 **부울입니다.**

## <a name="see-also"></a>참고 항목

- [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)
- [데이터 형식](../../javascript/data-types-javascript.md)
- [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)
- [데이터 복사, 전달 및 비교](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)