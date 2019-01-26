---
title: IDebugPointerObject::Dereference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e74273d25e121ec769207d429a622eed19654a92
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922888"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
가리키는 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwIndex`  
 [in] 개체의 시작 부분에서 간단한 바이트 오프셋을 지정 합니다.  
  
 `ppObject`  
 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 있으면를 가리키는 plus 오프셋을 나타내는 개체를 개체.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다. 이 개체가 다른 개체를 가리키지 않을 경우 E_FAIL을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 기본 형식 또는 클래스 또는 구조체와 같은 보다 복잡 한 형식을 가리키는 개체가 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)