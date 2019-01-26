---
title: MODULE_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 32b0e89a69bc39e43d4ff4fbc4e8f4d5816565ad
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975389"
---
# <a name="moduleflags"></a>MODULE_FLAGS
모듈에 설명 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
typedef DWORD MODULE_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
```  
  
## <a name="members"></a>멤버  
 MODULE_FLAG_NONE  
 모듈이 없는 지정합니다.  
  
 MODULE_FLAG_SYSTEM  
 시스템 모듈을 지정합니다.  
  
 MODULE_FLAG_SYMBOLS  
 기호 모듈을 지정합니다.  
  
 MODULE_FLAG_64BIT  
 64 비트 모듈을 지정합니다.  
  
 MODULE_FLAG_OPTIMIZED  
 최적화 된 모듈을 지정 합니다. 이 상태에 반영 되는 **모듈** 창입니다.  
  
 MODULE_FLAG_UNOPTIMIZED  
 최적화 되지 않은 모듈을 지정 합니다. 이 상태에 반영 되는 **모듈** 창입니다. 기본 상태입니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 합니다 `m_dwModuleFlags` 의 멤버는 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) 구조입니다.  
  
 이러한 플래그는 비트과 결합 될 수 `OR`입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)