---
title: IDebugProcessQueryProperties | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessQueryProperties
ms.assetid: ce29a248-81a0-42c0-99a7-1606e8c548ec
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5bfdca9a60061e2e519f0e98db9864ecae06b7c0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021769"
---
# <a name="idebugprocessqueryproperties"></a>IDebugProcessQueryProperties
이 인터페이스는 한 확장 인터페이스를 구현한 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 구현 합니다. 구현 자가 디버깅 프로세스 환경에 대 한 정보를 가져올 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProcessQueryProperties: IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버깅 프로세스의 실행 환경에 대 한 정보를 가져오는이 인터페이스를 구현 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProcessQueryProperties`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[QueryProperty](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperty.md)|속성 값을 쿼리 합니다.|  
|[QueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties.md)|속성 값에 대해 쿼리 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 구현 거의 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Portpriv.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)