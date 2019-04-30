---
title: IDebugProperty2::GetMemoryBytes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetMemoryBytes
helpviewer_keywords:
- IDebugProperty2::GetMemoryBytes
ms.assetid: b32042ed-7a06-4b4a-99ef-fe03b0aa61cc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 12d35ace2d5a2b2f0c10d4b2e0a44a05f52942fd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916660"
---
# <a name="idebugproperty2getmemorybytes"></a>IDebugProperty2::GetMemoryBytes
속성의 값을 구성 하는 메모리 바이트 수를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetMemoryBytes ( 
   IDebugMemoryBytes2** ppMemoryBytes
);
```

```csharp
int GetMemoryBytes ( 
   out IDebugMemoryBytes2 ppMemoryBytes
);
```

#### <a name="parameters"></a>매개 변수
 `ppMemoryBytes`

 [out] 반환 된 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) 속성의 값을 포함 하는 메모리를 검색 하는 데 사용할 수 있습니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 반환 `S_GETMEMORYBYTES_NO_MEMORY_BYTES` 검색할 메모리 바이트가 없는 경우.

## <a name="see-also"></a>참고 항목
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)