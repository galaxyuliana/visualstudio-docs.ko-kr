---
title: IDebugField::Equal | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7fdfc2abd407c586c949ade4e8085e282fb465a8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984355"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
이 메서드는 같음에 대 한 지정된 된 필드를 사용 하 여이 필드를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```csharp  
int Equal(  
   IDebugField pField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pField`  
 [in] 이 이와 비교할 필드입니다.  
  
## <a name="return-value"></a>반환 값  
 필드 같으면 반환 `S_OK`합니다. 필드를 다른 경우 반환 `S_FALSE.` 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)