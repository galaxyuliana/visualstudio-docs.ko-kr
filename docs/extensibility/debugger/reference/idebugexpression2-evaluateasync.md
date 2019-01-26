---
title: IDebugExpression2::EvaluateAsync | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpression2::EvaluateAsync
helpviewer_keywords:
- IDebugExpression2::EvaluateAsync
ms.assetid: 848fe6cb-0759-42f2-890b-d2b551c527d6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd01cb13b302269a3a6d91fda14713d8a1412a45
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070748"
---
# <a name="idebugexpression2evaluateasync"></a>IDebugExpression2::EvaluateAsync
이 메서드는 비동기적으로 식을 계산 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EvaluateAsync (   
   EVALFLAGS             dwFlags,  
   IDebugEventCallback2* pExprCallback  
);  
```  
  
```csharp  
int EvaluateAsync(  
   enum_EVALFLAGS       dwFlags,   
   IDebugEventCallback2 pExprCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 [in] 플래그의 조합 된 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 식 계산을 제어 하는 열거형입니다.  
  
 `pExprCallback`  
 [in] 이 매개 변수는 항상 null 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 일반적인 오류 코드가입니다.  
  
|Error|설명|  
|-----------|-----------------|  
|E_EVALUATE_BUSY_WITH_EVALUATION|다른 식이 계산 되는 현재 및 동시 식 계산에 사용할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 식 평가 시작 된 후에 즉시 반환 해야 합니다. 식이 성공적으로 계산 하는 경우는 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 보내야 합니다 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 이벤트 콜백을 통해 제공 [연결 ](../../../extensibility/debugger/reference/idebugprogram2-attach.md) 나 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한에 대 한이 메서드를 구현 하는 방법을 보여 줍니다 `CExpression` 를 구현 하는 개체를 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스입니다.  
  
```cpp  
HRESULT CExpression::EvaluateAsync(EVALFLAGS dwFlags,  
                                   IDebugEventCallback2* pExprCallback)  
{  
    // Set the aborted state to FALSE  
    // in case the user tries to redo the evaluation after aborting.  
    m_bAborted = FALSE;  
    // Post the WM_EVAL_EXPR message in the message queue of the current thread.  
    // This starts the expression evaluation on a background thread.  
    PostThreadMessage(GetCurrentThreadId(), WM_EVAL_EXPR, 0, (LPARAM) this);  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)