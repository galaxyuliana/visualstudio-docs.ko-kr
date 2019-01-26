---
title: IDebugBoundBreakpoint2::SetPassCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBoundBreakpoint2::SetPassCount
helpviewer_keywords:
- SetPassCount method
- IDebugBoundBreakpoint2::SetPassCount method
ms.assetid: b32c12f9-b34d-43bd-a1b9-61af6cf8e51b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f8285b0a348809d6eed972f87ea36958b76d086
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54944650"
---
# <a name="idebugboundbreakpoint2setpasscount"></a>IDebugBoundBreakpoint2::SetPassCount
설정 하거나이 바인딩된 중단점과 연결 된 통과 수를 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
```csharp  
int SetPassCount(   
   BP_PASSCOUNT bpPassCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bpPassCount`  
 [in] 합니다 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 패스 개수를 지정 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태 설정 됩니다 `BPS_DELETED` (부분 합니다 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형)입니다.  
  
## <a name="remarks"></a>설명  
 패스 개수 중단점이 발생 하는 경우를 결정 합니다. 현재 패스 또는 적중된 횟수를 호출 하 여 얻을 수 있습니다 합니다 [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md) 메서드.  
  
 이 중단점을 사용 하 여 이전에 연관 된 모든 패스 개수는 손실 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)