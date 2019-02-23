---
title: IDebugModule3::SetJustMyCodeState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::SetJustMyCodeState
helpviewer_keywords:
- IDebugModule3::SetJustMyCodeState
ms.assetid: 68f8166d-ef64-49ae-ad5e-79604f43bbd4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ef9c9b01ab37cce527e55696210438fcaaff9d2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697730"
---
# <a name="idebugmodule3setjustmycodestate"></a>IDebugModule3::SetJustMyCodeState
여부 사용자 코드도 모듈을 표시 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetJustMyCodeState(
   BOOL fIsUserCode
);
```

```csharp
int SetJustMyCodeState(
   int fIsUserCode
);
```

#### <a name="parameters"></a>매개 변수
 `fIsUserCode`

 [in] 0이 아닌 값 (`TRUE`) 사용자 코드 모듈을 고려해 야, 경우에 0 (`FALSE`) 하지 않아야 하는 경우.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)