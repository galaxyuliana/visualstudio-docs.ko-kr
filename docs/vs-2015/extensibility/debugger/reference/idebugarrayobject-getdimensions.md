---
title: IDebugArrayObject::GetDimensions | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetDimensions
helpviewer_keywords:
- IDebugArrayObject::GetDimensions method
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 09902c60f87cfb92d0f0778fcbd106ade4d8dac4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58982776"
---
# <a name="idebugarrayobjectgetdimensions"></a>IDebugArrayObject::GetDimensions
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

배열의 차수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetDimensions(   
   DWORD dwCount,  
   DWORD dwDimensions[]  
);  
```  
  
```csharp  
int GetDimensions(  
   [In] uint    dwCount,   
   [Out] uint[] dwDimensions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCount`  
 [in] 차원 검색할 수입니다.  
  
 `dwDimensions`  
 [out에서] 각 차원 크기를 사용 하 여 입력은 배열입니다. `dwCount` 최대 크기를 지정 된 `dwDimensions` 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 다차원 배열의 각 차원에 대 한 다양 한 크기를 가질 수 있습니다. 예를 들어 3 차원 배열의 지정 된 `myarray[3][2][6]`, 3, 2 및 6에서이 메서드는 반환 된 `dwDimensions` 순서 대로 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
