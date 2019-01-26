---
title: IEnumDebugPropertyInfo2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugPropertyInfo2::Reset
helpviewer_keywords:
- IEnumDebugPropertyInfo2::Reset
ms.assetid: fa4201c1-4633-4596-93aa-bd415c4ed71a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f49b1ca747e1b8ae17ffdd9837c7c061e51e1431
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55068877"
---
# <a name="ienumdebugpropertyinfo2reset"></a>IEnumDebugPropertyInfo2::Reset
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
 이 메서드를 호출한 후, 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)