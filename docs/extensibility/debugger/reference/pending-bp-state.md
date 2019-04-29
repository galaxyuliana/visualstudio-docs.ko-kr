---
title: PENDING_BP_STATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PENDING_BP_STATE
helpviewer_keywords:
- PENDING_BP_STATE enumeration
ms.assetid: ac04ad72-fa92-4a15-ade2-0d0bbbadfc7f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ab1e9345cf599c4336b202d32fb71a9097fe629
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913612"
---
# <a name="pendingbpstate"></a>PENDING_BP_STATE
보류 중인 중단점 (아직 바인딩되지 않은 중단점)의 상태를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_PENDING_BP_STATE { 
   PBPS_NONE     = 0x0000,
   PBPS_DELETED  = 0x0001,
   PBPS_DISABLED = 0x0002,
   PBPS_ENABLED  = 0x0003
};
typedef DWORD PENDING_BP_STATE;
```

```csharp
public enum enum_PENDING_BP_STATE { 
   PBPS_NONE     = 0x0000,
   PBPS_DELETED  = 0x0001,
   PBPS_DISABLED = 0x0002,
   PBPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>멤버
 0 PBPS_NONE 자리 표시자입니다. 이 값은 반환 되지 않습니다.

 PBPS_DELETED 보류 중인 중단점 삭제 된 것을 나타냅니다.

 PBPS_DISABLED 보류 중인 중단점은 사용 되지 않음을 나타냅니다.

 PBPS_ENABLED 보류 중단점이 설정 되었음을 나타냅니다.

## <a name="remarks"></a>설명
 으로 사용 합니다 `state` 의 멤버는 [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) 구조.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)