---
title: IDebugEngine2::DestroyProgram | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::DestroyProgram
helpviewer_keywords:
- IDebugEngine2::DestroyProgram
ms.assetid: 0c9e2698-c70f-4770-a7bb-39650e9c3a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e02cd777e3ff363ef17234367be401cf39ea9952
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031710"
---
# <a name="idebugengine2destroyprogram"></a>IDebugEngine2::DestroyProgram
지정 된 프로그램 예외적인 종료 되었습니다 하 고는 DE 프로그램에 대 한 모든 참조를 정리 해야 하는 디버그 엔진 (DE) 알리고 프로그램 송신 이벤트를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DestroyProgram(   
   IDebugProgram2* pProgram  
);  
```  
  
```cpp  
int DestroyProgram(   
   IDebugProgram2 pProgram  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 예외적인 종료 하는 프로그램을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 DE 계속 해 서 보내면이 메서드를 호출한 후는 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 이벤트 세션 디버그 관리자 (SDM).  
  
 이 메서드가 구현 되지 않습니다 (반환 `E_NOTIMPL`)는 DE 디버그 중인 프로그램과 동일한 프로세스에서 실행 되는 경우. 이 메서드는 DE SDM와 동일한 프로세스에서 실행 하는 경우에 구현 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)