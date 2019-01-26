---
title: IDebugModuleLoadEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugModuleLoadEvent2
helpviewer_keywords:
- IDebugModuleLoadEvent2 interface
ms.assetid: 7d26fb23-5d49-4ba7-b7c5-3aed4d7be81e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8fc70ffa1827c69df1567b7f667031b629dcb8bc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918696"
---
# <a name="idebugmoduleloadevent2"></a>IDebugModuleLoadEvent2
이 인터페이스를 모듈 로드 되거나 언로드될 때 디버그 엔진 (DE)에서 세션 디버그 관리자 (SDM)에 전송 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugModuleLoadEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 모듈 로드 또는 언로드되는 보고서에이 인터페이스를 구현 합니다. 합니다 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 합니다. SDM 사용 [QueryInterface](/cpp/atl/queryinterface) 액세스는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 DE 만들고이 이벤트 개체를 모듈을 로드 하거나 언로드한 보고서를 보냅니다. 이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버그 중인 프로그램에 연결 될 때 SDM에서 제공 하는 콜백 함수.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서 메서드의 `IDebugModuleLoadEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)|되는 모듈을 가져옵니다 로드 또는 언로드 합니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio에서이 이벤트를 사용 하 여 유지 하는 **모듈** 최신 창입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)