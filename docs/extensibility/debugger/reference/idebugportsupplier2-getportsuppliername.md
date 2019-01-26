---
title: IDebugPortSupplier2::GetPortSupplierName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::GetPortSupplierName
helpviewer_keywords:
- IDebugPortSupplier2::GetPortSupplierName
ms.assetid: e4c368ab-640d-4b5b-9f74-810dc9364d8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d092cc049a65ba4f232c9aefd00536a78115b5b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022406"
---
# <a name="idebugportsupplier2getportsuppliername"></a>IDebugPortSupplier2::GetPortSupplierName
포트 공급자 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortSupplierName(   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetPortSupplierName(   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrName`  
 [out] 포트 공급자의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)