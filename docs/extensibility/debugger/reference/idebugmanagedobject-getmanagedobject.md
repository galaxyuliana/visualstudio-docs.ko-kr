---
title: IDebugManagedObject::GetManagedObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugManagedObject::GetManagedObject
helpviewer_keywords:
- IDebugManagedObject::GetManagedObject method
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2be150d3ce1103f8f47438af7ac8fcfcba8519da
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922914"
---
# <a name="idebugmanagedobjectgetmanagedobject"></a>IDebugManagedObject::GetManagedObject
관리 되는 개체를 나타내는 인터페이스를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetManagedObject(   
   IUnknown** ppManagedObject  
);  
```  
  
```cpp  
int GetManagedObject(  
   out object ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppManagedObject`  
 [out] 관리 되는 개체를 나타내는 인터페이스를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 해당 메서드를 호출할 수 있도록 관리 되는 클래스에서 구현 되는 모든 인터페이스에 대 한이 메서드에서 반환 된 인터페이스를 쿼리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)