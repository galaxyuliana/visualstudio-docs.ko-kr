---
title: BP_STATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4117b3cb92eef555d5ed9a6c3e829fb3302924ae
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709254"
---
# <a name="bpstate"></a>BP_STATE
바인딩된 중단점의 존재 여부를 지정 하 고 또한 사용 되는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
typedef DWORD BP_STATE;
```

```csharp
public enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>멤버
중단점이 없는 BPS_NONE 지정 합니다.

BPS_DELETED 중단점 삭제 된 것을 지정 합니다.

BPS_DISABLED 중단점은 사용 되지 않음을 지정 합니다.

BPS_ENABLED 중단점이 설정 되었음을 지정 합니다.

## <a name="remarks"></a>설명
반환 된 [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)
