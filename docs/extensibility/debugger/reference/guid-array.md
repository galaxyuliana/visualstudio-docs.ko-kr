---
title: GUID_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eed39ee4446e66e1e7b1700d97ad680eb62c2523
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704971"
---
# <a name="guidarray"></a>GUID_ARRAY
사용할 디버그 엔진에 대 한 고유 식별자의 배열을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct tagGUID_ARRAY
{
    DWORD dwCount;
    GUID *Members;
} GUID_ARRAY;
```

```csharp
public struct GUID_ARRAY
{
    public uint dwCount;
    public Guid Members;
}
```

## <a name="terms"></a>용어
dwCount 배열에 있는 고유 식별자의 수입니다.

고유 식별자가 포함 된 멤버의 배열입니다.

## <a name="remarks"></a>설명
이 구조에서 반환 되는 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: Msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)
