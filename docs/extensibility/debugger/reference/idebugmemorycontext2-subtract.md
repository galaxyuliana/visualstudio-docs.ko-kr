---
title: IDebugMemoryContext2::Subtract | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 53f919cb0c70d93c9888eb979846bc9b228c2e18
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035356"
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
현재 컨텍스트에서 지정된 된 값을 빼고 새 컨텍스트를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Subtract(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Subtract(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCount`  
 [in] 감소 시킬 메모리 바이트의 수입니다.  
  
 `ppMemCxt`  
 [out] 반환 된 새 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 메모리 컨텍스트 주소, 이므로 주소에서 값을 빼면 주소가 생성 되는 새 필요한 새 상황에 맞는 인터페이스.  
  
 항상이 메서드는 만들어진 주소 외부 메모리 공간이이 컨텍스트와 연결 된 경우에 새 컨텍스트를을 생성 해야 합니다. 새 컨텍스트에 없는 메모리를 할당할 수 있습니다 하거나이 유일한 예외는 `ppMemCxt` null 값인 경우 (즉, 오류).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)