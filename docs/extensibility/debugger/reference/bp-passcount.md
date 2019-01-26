---
title: BP_PASSCOUNT | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b1586e9bd8f0a33eb0b11370e81d283381e91866
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920458"
---
# <a name="bppasscount"></a>BP_PASSCOUNT
조건부 중단점을 발생 횟수 및 조건을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>멤버  
 `dwPassCount`  
 이 발생 하기 전에 중단점을 통해 전달 횟수입니다.  
  
 `stylePassCount`  
 값을 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) 중단점의 스타일을 지정 하는 열거형 전달할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 멤버인 합니다 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 구조입니다.  
  
 이 구조를 매개 변수로 전달 되는[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) 하 고[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)