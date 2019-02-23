---
title: IEnumDebugObjects::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::Skip
helpviewer_keywords:
- IEnumDebugObjects::Skip method
ms.assetid: 957cead8-0a9c-4403-b190-b9fbadc49d42
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 41865780df808231b929ef775d4e967b8c608595
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687001"
---
# <a name="ienumdebugobjectsskip"></a>IEnumDebugObjects::Skip
이 메서드는 지정 된 개수의 요소를 건너뜁니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Skip(
   [in] ULONG celt
);
```

```csharp
int Skip(
   [In] uint celt
);
```

#### <a name="parameters"></a>매개 변수
 `celt`

 [in] 건너뛸 요소 수입니다.

## <a name="return-value"></a>반환 값
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우 `celt` 나머지 요소 수보다 큽니다; 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 하는 경우 `celt` 수보다 큰 값 끝에 설정 되어 나머지 요소를 열거 및 `S_FALSE` 반환 됩니다.

## <a name="see-also"></a>참고 항목
- [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)