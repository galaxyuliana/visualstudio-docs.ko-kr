---
title: IDebugReference2::SetReferenceType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugReference2::SetReferenceType
helpviewer_keywords:
- IDebugReference2::SetReferenceType
ms.assetid: 5854a172-ea82-481c-97d9-c7fc16923d44
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c73ef6fb192f1b2e5538a3ad020147a6d8836678
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021613"
---
# <a name="idebugreference2setreferencetype"></a>IDebugReference2::SetReferenceType
참조 형식을 설정합니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetReferenceType (   
   REFERENCE_TYPE dwRefType  
);  
```  
  
```csharp  
int SetReferenceType (   
   enum_REFERENCE_TYPE dwRefType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwRefType`  
 [in] 값을 [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md) 참조 형식을 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md)