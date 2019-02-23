---
title: IDebugObject::IsEqual | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 49d909dc0896bcc1b130ce908699c04ad9543c73
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691113"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
이 개체를 사용 하 여 개체를 비교합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsEqual( 
   IDebugObject* pObject,
   BOOL*         pfIsEqual
);
```

```csharp
int IsEqual(
   IDebugObject pObject,
   out int      pfIsEqual
);
```

#### <a name="parameters"></a>매개 변수
 `pObject`

 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 비교할 개체를 나타내는 개체입니다.

 `pfIsEqual`

 [out] 0이 아닌 값을 반환 합니다 (`TRUE`) 개체의 값이 고 그렇지 않으면 동일한 경우 0을 반환 합니다 (`FALSE`).

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 이 메서드 주소를 나타내는 값을 비교할 수는 일반적으로 `pObject` 매개 변수 및이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체; 주소가 같지 않으면 개체는 같은 간주 될 수 있습니다.

## <a name="see-also"></a>참고 항목
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)