---
title: ATTACH_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6d5a7cb8cfbc4efc2ffd90a58c0c0650b677ed8d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54966285"
---
# <a name="attachreason"></a>ATTACH_REASON
프로그램 노드를 연결 하는 디버그 엔진 (DE)에 대 한 이유를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 ATTACH_REASON_AUTO  
 프로세스 디버그 모드에서 현재 이므로 연결 합니다.  
  
 ATTACH_REASON_LAUNCH  
 프로세스가 시작 된 때문에 연결 합니다.  
  
 ATTACH_REASON_USER  
 사용자 요청으로 인해 연결 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값은 매개 변수로 사용 합니다 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 하 고 [연결](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)