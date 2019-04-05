---
title: IDebugBinder3::GetAllAliases | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBinder3::GetAllAliases
helpviewer_keywords:
- IDebugBinder3::GetAllAliases method
ms.assetid: 1f9ab2ee-2ab3-4a61-8b99-95dd7fdf3511
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dc2075ccc37d280640f7559b1454990ee6684f25
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58980679"
---
# <a name="idebugbinder3getallaliases"></a>IDebugBinder3::GetAllAliases
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 프로그램에서 별칭 목록을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAllAliases(  
   UINT          uRequest,  
   IDebugAlias** ppAliases,  
   UINT*         puFetched  
);  
```  
  
```csharp  
int GetAllAliases(  
   uint          uRequest,   
   IDebugAlias[] ppAliases,   
   out uint      puFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uRequest`  
 [in] 반환할 별칭의 최대 수 (에 전달 된 배열의 길이 지정 `ppAliases`).  
  
 `ppAliases`  
 [out에서] 별칭으로 채워질 배열 (null 값인 경우 및 `uRequest` 가 0 이면 반환 될 수 있는 별칭 수에서 반환할 `puFetched`).  
  
 `puFetched`  
 [out] 가져올 별칭의 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
