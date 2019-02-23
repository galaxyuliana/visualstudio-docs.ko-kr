---
title: IDebugStackFrame2::GetThread | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetThread
helpviewer_keywords:
- IDebugStackFrame2::GetThread
ms.assetid: cbeef85b-3dd7-4f97-adc2-c4d197d979fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 99248291ce06aa4f07f627429bbb5cc2993a61c1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718172"
---
# <a name="idebugstackframe2getthread"></a>IDebugStackFrame2::GetThread
스택 프레임과 연결 된 스레드를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetThread ( 
   IDebugThread2** ppThread
);
```

```csharp
int GetThread ( 
   out IDebugThread2 ppThread
);
```

#### <a name="parameters"></a>매개 변수
 `ppThread`

 [out] 반환 된 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 스레드를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)