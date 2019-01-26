---
title: IDebugClassField::GetEnclosingClass | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 37dcb0eb23cf216b604d927309cd395252d59792
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040868"
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
이 클래스를 포함 하는 클래스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEnclosingClass(   
   IDebugClassField** ppClassField  
);  
```  
  
```csharp  
int GetEnclosingClass(  
   out IDebugClassField ppClassField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppClassField`  
 [out] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 바깥쪽을 나타내는 개체 클래스. 바깥쪽 클래스에 없는 경우 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 표시 되는 클래스 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 개체는 중첩된 클래스를 해당 `ppClassField` 매개 변수 반환는 `IDebugClassField` 바깥쪽을 나타내는 개체 클래스. 예를 들어 다음과 같습니다.이 클래스 정의  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 호출을 `GetEnclosingClass` 메서드를 `IDebugClassField` 나타내는 개체입니다는 `NestedClass` 반환 클래스는 `IDebugClassField` 클래스를 나타내는 개체 `RootClass`.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)