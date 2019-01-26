---
title: IDebugObject::IsProxy | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugObject::IsProxy
- IsProxy
ms.assetid: 06c66b87-db95-4400-ab26-5d33e743a439
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b32fcff6a365f37c926194560674da354f0f08ee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918721"
---
# <a name="idebugobjectisproxy"></a>IDebugObject::IsProxy
투명 프록시 개체 인지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsProxy (  
   BOOL* pfIsProxy  
);  
```  
  
```csharp  
int IsProxy (  
   out bool pfIsProxy  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsProxy`  
 [out] `TRUE` 개체가 투명 프록시; 있으면이 고, 그렇지 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 기본 c + + 디버그 엔진에 의해 구현 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)