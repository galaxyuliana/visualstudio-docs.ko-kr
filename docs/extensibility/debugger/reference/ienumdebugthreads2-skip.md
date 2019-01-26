---
title: IEnumDebugThreads2::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugThreads2::Skip
helpviewer_keywords:
- IEnumDebugThreads2::Skip
ms.assetid: eab068d4-1f8d-44cd-bc54-92a10fe23de6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d8cf2821e9440c110aaba9dcf6fa6642df4ec9e8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939805"
---
# <a name="ienumdebugthreads2skip"></a>IEnumDebugThreads2::Skip
지정 된 개수의 요소를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
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
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)