---
title: IEnumDebugThreads2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugThreads2::Reset
helpviewer_keywords:
- IEnumDebugThreads2::Reset
ms.assetid: 88980d9a-c4d6-4de4-a9ab-fb56fa71394a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 83660f3689f34e9893c91c0a65dece64fa373cab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989876"
---
# <a name="ienumdebugthreads2reset"></a>IEnumDebugThreads2::Reset
첫 번째 요소를 열거를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출한 후, 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)