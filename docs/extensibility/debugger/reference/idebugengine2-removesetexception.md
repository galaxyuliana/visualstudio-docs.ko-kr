---
title: IDebugEngine2::RemoveSetException | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d23e0d60d19d5c163d1bbd7856750719e3712d78
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040894"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
지정된 된 예외를 제거 하 여 디버그 엔진에서 더 이상 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RemoveSetException(   
   EXCEPTION_INFO* pException  
);  
```  
  
```csharp  
int RemoveSetException(   
   EXCEPTION_INFO[] pException  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pException`  
 [in] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 제거할 예외를 설명 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 제거 되는 예외 설정 되어 있어야 이전에 대 한 이전 호출에서 합니다 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 메서드.  
  
 모든 집합 예외를 한 번에 제거를 호출 합니다 [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)