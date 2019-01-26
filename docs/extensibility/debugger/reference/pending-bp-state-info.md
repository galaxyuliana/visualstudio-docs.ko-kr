---
title: PENDING_BP_STATE_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7cea960e35b0ff56720f8c687fafdea1fe8e6a6e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991387"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
코드 위치에 바인딩할 수 있는 중단점의 상태에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagPENDING_BP_STATE_INFO {   
   PENDING_BP_STATE       state;  
   PENDING_BP_STATE_FLAGS flags;  
} PENDING_BP_STATE_INFO;  
```  
  
```csharp  
public struct PENDING_BP_STATE_INFO {   
   public uint state;  
   public uint flags;  
};  
```  
  
## <a name="members"></a>멤버  
 상태  
 값을 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) 보류 중인 중단점의 상태를 지정 하는 열거형입니다.  
  
 플래그  
 플래그의 조합 된 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) 중단점 가상화 되 고 있는지 여부를 지정 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 이 구조에 전달 되는 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) 메서드 위치에서 채워집니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)   
 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)   
 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)