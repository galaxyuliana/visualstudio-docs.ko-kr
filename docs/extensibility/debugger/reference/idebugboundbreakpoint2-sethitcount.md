---
title: IDebugBoundBreakpoint2::SetHitCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: abda1b2544f93577f7355b60c07143c623da181e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931585"
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
바인딩된 중단점의 적중된 횟수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```csharp  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwHitCount`  
 [in] 설정 하려면 적중된 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태 설정 됩니다 `BPS_DELETED` (부분 합니다 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형)입니다.  
  
## <a name="remarks"></a>설명  
 적중된 횟수가 세션의 현재 실행 하는 동안이 중단점이 발생 한 횟수입니다.  
  
 이 메서드는 일반적으로이 중단점에서 현재 적중된 횟수를 업데이트 하려면 디버그 엔진에 의해 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)