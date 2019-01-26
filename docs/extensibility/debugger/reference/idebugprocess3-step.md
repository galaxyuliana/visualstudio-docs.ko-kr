---
title: IDebugProcess3::Step | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Step
helpviewer_keywords:
- IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c1b9dc08812722f843c091e1c87835377eb0621e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025321"
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
하나의 명령 또는 문을 실행 하는 프로세스를 하면 됩니다.  
  
> [!NOTE]
>  이 메서드를 대신 사용 해야 [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Step(  
   IDebugThread2* pThread,  
   STEPKIND       sk,  
   STEPUNIT       step,  
);  
```  
  
```csharp  
int Step(  
   IDebugThread2 pThread,   
   enum_STEPKIND sk,   
   enum_STEPUNIT step  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 단계별 중인 스레드를 나타내는 개체입니다.  
  
 `sk`  
 [in] 중 하나는 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) 값입니다.  
  
 `step`  
 [in] 중 하나는 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 발생 한 경우 모든 스레드 동기화 또는 스레드 간 통신, 특정 스레드에서 단계별로 실행할 때 프로세스의 다른 스레드를 실행 해야 합니다.  
  
 **경고** stopping 이벤트 또는 직접 (동기) 이벤트를 전송 하지 마십시오 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)   
 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)