---
title: IDebugStackFrame3::GetUnwindCodeContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame3::GetUnwindCodeContext
helpviewer_keywords:
- IDebugStackFrame3::GetUnwindCodeContext method
ms.assetid: b25f7e7d-2b24-48e4-93b3-829e61d73ebf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 032e7f05ebb1ba8367ffaa7ef1ffbfb974aa0df1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54933570"
---
# <a name="idebugstackframe3getunwindcodecontext"></a>IDebugStackFrame3::GetUnwindCodeContext
코드 컨텍스트 스택을 해제 작업 하는 경우 위치를 나타내는 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetUnwindCodeContext(  
   IDebugCodeContext2 **ppCodeContext  
);  
```  
  
```csharp  
int GetUnwindCodeContext(  
   out IDebugCodeContext2 ppCodeContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppCodeContext`  
 [out] 반환 된 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 스택 해제가 발생 한 경우 코드 컨텍스트 위치를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 스택 해제 후 위치에 대 한 코드 컨텍스트를 반환할 수 있습니다, 경우에이 반드시 스택 해제 현재 스택 프레임에서 실제로 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)