---
title: PENDING_BP_STATE_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b4c19bed895a04e372f930d347a7caa761d34a56
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865366"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
코드 위치에 바인딩할 수 있는 중단점의 상태에 대 한 정보를 포함 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct _tagPENDING_BP_STATE_INFO { 
   PENDING_BP_STATE       state;
   PENDING_BP_STATE_FLAGS flags;
} PENDING_BP_STATE_INFO;
```

```csharp
public struct PENDING_BP_STATE_INFO { 
   public uint state;
   public uint flags;
};
```

## <a name="members"></a>멤버
 상태에서 값을 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) 보류 중인 중단점의 상태를 지정 하는 열거형입니다.

 플래그의 조합에 플래그를 지정 합니다 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) 중단점 가상화 되 고 있는지 여부를 지정 하는 열거형입니다.

## <a name="remarks"></a>설명
 이 구조에 전달 되는 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) 메서드 위치에서 채워집니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)
- [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)
- [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)