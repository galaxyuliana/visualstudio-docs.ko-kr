---
title: IDebugField::GetType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetType
helpviewer_keywords:
- IDebugField::GetType method
ms.assetid: b3cdec9f-ef7b-44d0-a775-d17ef7eae968
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a47ae50baf0ea906815a0a95b8eccb3668ec7c40
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55007560"
---
# <a name="idebugfieldgettype"></a>IDebugField::GetType
이 메서드는 필드의 형식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetType(   
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetType(  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppType`  
 [out] 다른 필드 형식을 반환 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)