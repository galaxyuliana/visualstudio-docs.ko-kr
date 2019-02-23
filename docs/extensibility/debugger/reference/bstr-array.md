---
title: BSTR_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BSTR_ARRAY
helpviewer_keywords:
- BSTR_ARRAY structure
ms.assetid: 48da37f7-a237-48a9-9ff9-389c1a00862c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 24222b60db1ba35da59069e58d6f1377928e7a54
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714922"
---
# <a name="bstrarray"></a>BSTR_ARRAY
문자열의 배열을 설명 하는 구조체입니다.

## <a name="syntax"></a>구문

```cpp
typedef struct tagBSTR_ARRAY {
    DWORD dwCount;
    BSTR* Members;
} BSTR_ARRAY;
```

```csharp
struct BSTR_ARRAY {
    DWORD    dwCount;
    string[] Members;
}
```

## <a name="terms"></a>용어
dwCount 개수의 문자열에서 `Members` 배열입니다.

멤버 문자열 배열입니다.

## <a name="remarks"></a>설명
이 구조에서 반환 되는 [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) 메서드.


 [C + + 전용] 사용 하 여 각 개별 문자열을 해제 해야 합니다 `SysFreeString`, 및 `Members` 배열을 사용 하 여 해제 해야 `CoTaskMemFree`합니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)
- [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)
