---
title: IDebugBinder::GetMemoryContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder::GetMemoryContext
helpviewer_keywords:
- IDebugBinder::GetMemoryContext method
ms.assetid: 801c5b60-acff-4822-b23d-e9c7bbca8a0f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fb90a9688f44c20a99292a1901812d8c3fbab64d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54916331"
---
# <a name="idebugbindergetmemorycontext"></a>IDebugBinder::GetMemoryContext
이 메서드는 메모리 컨텍스트 개체 위치 이거나 메모리 주소를 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemoryContext(   
   IDebugField*           pField,  
   DWORD                  dwConstant,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int GetMemoryContext(  
   IDebugField              pField,   
   uint                     dwConstant,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 찾을 개체를 설명 합니다. 하는 경우 `NULL`를 사용 하 여 `dwConstant` 대신 합니다.  
  
 `dwConstant`  
 [in] 0x5000 같은 상수 메모리 주소입니다.  
  
 `ppMemCxt`  
 [out] 반환 된 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체의 주소나 메모리 주소를에서 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)