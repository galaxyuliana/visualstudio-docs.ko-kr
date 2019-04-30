---
title: IDebugArrayObject::GetRank | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0391030e77e5959fdc28c94f63e099e5c505d77
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923730"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
배열의 차원 수, 차수를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

#### <a name="parameters"></a>매개 변수
 `pdwRank`

 [out] 순위를 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 사용 된 [GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) 배열 개체의 각 차원 크기를 검색 하는 방법입니다.

## <a name="see-also"></a>참고 항목
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)