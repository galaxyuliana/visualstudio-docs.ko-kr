---
title: PROGRAM_NODE_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROGRAM_NODE_ARRAY
helpviewer_keywords:
- PROGRAM_NODE_ARRAY structure
ms.assetid: 8eeea600-eda5-4b7c-868a-0b86d177b0a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9af33dd296c222a6ab187097437e3774d2bbdbd4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913446"
---
# <a name="programnodearray"></a>PROGRAM_NODE_ARRAY
흥미로운 프로그램을 설명 하는 개체의 배열을 포함 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct tagPROGRAM_NODE_ARRAY {
   DWORD                dwCount;
   IDebugProgramNode2** Members;
} PROGRAM_NODE_ARRAY;
```

```csharp
public struct tagPROGRAM_NODE_ARRAY {
   public uint                 dwCount;
   public IDebugProgramNode2[] Members;
}
```

## <a name="members"></a>멤버
 dwCount 개체 수에는 `Members` 배열입니다.

 멤버의 배열을 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 요청한 프로그램을 설명 하는 개체입니다.

## <a name="remarks"></a>설명
 이 구조체의 일부인 합니다 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) 다시 채워집니다를 호출 하 여 구조를 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) 메서드.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)