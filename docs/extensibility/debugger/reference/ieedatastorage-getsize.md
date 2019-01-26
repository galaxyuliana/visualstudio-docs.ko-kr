---
title: IEEDataStorage::GetSize | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 71644b1b6e056a122e96377ffa62942e46f3a9d9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54964628"
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
이 개체에 포함 된 바이트 수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSize(  
   ULONG* size  
);  
```  
  
```csharp  
int GetSize(  
   out uint size  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `size`  
 [out] 이 개체에 포함 된 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 사용 된 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md) 실제 데이터 바이트를 검색 하는 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)