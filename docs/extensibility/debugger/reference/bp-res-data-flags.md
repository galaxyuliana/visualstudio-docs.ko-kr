---
title: BP_RES_DATA_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RES_DATA_FLAGS
helpviewer_keywords:
- BP_RES_DATA_FLAGS enumeration
ms.assetid: d97611e2-def6-45a9-ad7d-eedf2ad4c82b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dfbf34af69accc3fa50e0648880b5f8633f1618a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714064"
---
# <a name="bpresdataflags"></a>BP_RES_DATA_FLAGS
데이터 중단점 에뮬레이트 여부 또는에서 구현 된 하드웨어를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_BP_RES_DATA_FLAGS {
    BP_RES_DATA_EMULATED = 0x0001
};
typedef DWORD BP_RES_DATA_FLAGS;
```

```csharp
public enum enum_BP_RES_DATA_FLAGS {
    BP_RES_DATA_EMULATED = 0x0001
};
```

## <a name="members"></a>멤버
BP_RES_DATA_EMULATED 데이터 중단점을 에뮬레이트 되는 것을 지정 합니다.

## <a name="remarks"></a>설명
에 사용 되는 합니다 `dwFlags` 의 멤버는 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) 구조입니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)
