---
title: IDebugBinder3::GetTypeArgumentCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetTypeArgumentCount
helpviewer_keywords:
- IDebugBinder3::GetTypeArgumentCount method
ms.assetid: caf68de6-6f7c-4efd-b803-121347a5032e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f0a3e0b67c120e4f0c6712c6e47e35e7c370cce
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948104"
---
# <a name="idebugbinder3gettypeargumentcount"></a>IDebugBinder3::GetTypeArgumentCount
이 메서드는이 개체와 연결 된 인수 형식의 수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeArgumentCount(  
   UINT* uCount  
);  
```  
  
```csharp  
int GetTypeArgumentCount(  
   out uint uCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uCount`  
 [out] 이 개체와 연결 된 인수 형식의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 되는 값 배열을 할당 하 여 사용에 대 한 데 사용할 수는 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)