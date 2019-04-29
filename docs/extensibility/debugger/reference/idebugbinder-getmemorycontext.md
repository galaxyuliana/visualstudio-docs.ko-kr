---
title: IDebugBinder::GetMemoryContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::GetMemoryContext
helpviewer_keywords:
- IDebugBinder::GetMemoryContext method
ms.assetid: 801c5b60-acff-4822-b23d-e9c7bbca8a0f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b7c647f12e80adab70dd626347d52e07505e3704
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877538"
---
# <a name="idebugbindergetmemorycontext"></a>IDebugBinder::GetMemoryContext
이 메서드는 메모리 컨텍스트 개체 위치 이거나 메모리 주소를 변환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetMemoryContext( 
   IDebugField*           pField,
   DWORD                  dwConstant,
   IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int GetMemoryContext(
   IDebugField              pField,
   uint                     dwConstant,
   out IDebugMemoryContext2 ppMemCxt
);
```

#### <a name="parameters"></a>매개 변수
 `pField`

 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 찾을 개체를 설명 합니다. 하는 경우 `NULL`를 사용 하 여 `dwConstant` 대신 합니다.

 `dwConstant`

 [in] 0x5000 같은 상수 메모리 주소입니다.

 `ppMemCxt`

 [out] 반환 된 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 개체의 주소나 메모리 주소를에서 나타내는 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)