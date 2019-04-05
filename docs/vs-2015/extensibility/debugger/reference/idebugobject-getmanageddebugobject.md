---
title: IDebugObject::GetManagedDebugObject | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4f2917135f5e25648cf08cd9030e3fdf31aedb52
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984813"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

디버그 엔진의 주소 공간에서 관리 되는 개체의 복사본을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppObject`  
 [out] 반환 된 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) 새로 만든된 관리 되는 개체를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다. 이 경우 E_FAIL을 반환 합니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 관리 되는 값 클래스 인스턴스를 나타내지 않습니다.  
  
## <a name="remarks"></a>설명  
 이렇게 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체는 같은 관리 되는 값 클래스 인스턴스를 나타내야 합니다는 `System.Decimal` 인스턴스. 호출의 오버 헤드가 로컬 복사본을 함으로써 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 제거 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)
