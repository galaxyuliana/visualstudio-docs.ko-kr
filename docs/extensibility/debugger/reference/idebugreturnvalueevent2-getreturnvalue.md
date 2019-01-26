---
title: IDebugReturnValueEvent2::GetReturnValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugReturnValueEvent2::GetReturnValue
helpviewer_keywords:
- IDebugReturnValueEvent2::GetReturnValue
ms.assetid: 86c50d5a-6df6-4798-818a-c587a8741f90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 069d72a25547750df27bc52536e0b119acae61db
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021639"
---
# <a name="idebugreturnvalueevent2getreturnvalue"></a>IDebugReturnValueEvent2::GetReturnValue
부재 중 또는 함수를 단계별로 실행에서 반환 되는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReturnValue (   
   IDebugProperty2** ppReturnValue  
);  
```  
  
```csharp  
int GetReturnValue (   
   out IDebugProperty2 ppReturnValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppReturnValue`  
 [out] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 검색할 값을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)