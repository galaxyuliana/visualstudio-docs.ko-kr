---
title: IDebugObject::GetMemoryContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject::GetMemoryContext
helpviewer_keywords:
- IDebugObject::GetMemoryContext method
ms.assetid: 6760a0d3-a898-4e81-b68f-c45c584b225b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9fe479c93cadeb6826ee4e4d3ba41ff973cb11c9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55027739"
---
# <a name="idebugobjectgetmemorycontext"></a>IDebugObject::GetMemoryContext
개체의 값의 주소를 나타내는 메모리 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemoryContext(   
   IDebugMemoryContext2** pContext  
);  
```  
  
```csharp  
int GetMemoryContext(  
   ref IDebugMemoryContext2 pContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pContext`  
 [out] 반환 된 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체의 값의 주소를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 표시 된 대로 값의 주소 지정 하는 반환 된 메모리 컨텍스트 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)