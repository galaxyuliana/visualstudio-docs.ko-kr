---
title: IDebugEngineProgram2::Stop | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e60b328ee13a47df9d7656c992f81e63cbbd2ed
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983783"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
이 프로그램에서 실행 중인 모든 스레드를 중지 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 다중 프로그램 환경에서이 프로그램을 디버깅 되는 호출 됩니다. 다른 프로그램에서 중지 이벤트를 수신 되 면이 메서드는이 프로그램에서 호출 됩니다. 이 메서드의 구현은 비동기; 여야 합니다. 즉, 모든 스레드는이 메서드가 반환 되기 전에 중지 해야 합니다. 이 메서드의 구현을 호출 처럼 간단할 수 있습니다 합니다 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 이 프로그램에는 메서드.  
  
 디버그 이벤트가 없습니다이 메서드에 대 한 응답으로 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)