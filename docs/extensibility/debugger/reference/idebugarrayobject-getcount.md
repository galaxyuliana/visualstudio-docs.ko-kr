---
title: IDebugArrayObject::GetCount | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 30419e20b6ac1519e3d9b278aabfcb012372d193
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923756"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

배열의 요소 개수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwElements`  
 [out] 개수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 배열 개체는 다차원 배열 하는 경우에 모든 배열 개체 요소의 1 차원 배열에으로 간주 합니다. 예를 들어, 배열의 지정 된 `myarray[3][2][6]`,이 메서드는 36 반환 된 `pdwElements` 매개 변수입니다. 사용 된 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) 메서드를 한 번에 하나씩 개별 요소를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
