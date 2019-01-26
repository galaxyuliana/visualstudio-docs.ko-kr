---
title: IDebugExceptionEvent2::CanPassToDebuggee | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ccf980fb3d5b357b6211674ca8b99132d81fae1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55041011"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
디버그 엔진 (DE) 실행을 다시 시작할 때 디버깅 중인 프로그램에이 예외를 전달 하는 옵션을 지원 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` (프로그램에 예외가 전달 수 있음) 또는 `S_FALSE` (예외 전달할 수 없습니다).  
  
## <a name="remarks"></a>설명  
 DE 디버기를 전달 하기 위한 기본 작업이 있어야 합니다. IDE 나타날 수는 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) 이벤트 및 호출 합니다 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md) 메서드를 호출 하지 않고는 `CanPassToDebuggee` 메서드. 따라서는 DE 여부 예외를 전달 하기 위한 기본 사례가 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)