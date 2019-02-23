---
title: IDebugObject2::GetICorDebugValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetICorDebugValue
helpviewer_keywords:
- IDebugObject2::GetICorDebugValue method
ms.assetid: bcd4355d-3fbe-483f-bb23-a44348323c6a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5f31436390225e022069ef69f1557f4752f8c208
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695365"
---
# <a name="idebugobject2geticordebugvalue"></a>IDebugObject2::GetICorDebugValue
이 개체와 연결 된 값을 나타내는 관리 코드 개체를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

#### <a name="parameters"></a>매개 변수
 `ppUnk`

 [out] `IUnknown` 이 별칭을 나타내는 인터페이스입니다. 이 인터페이스를 쿼리할 수는 `ICorDebugValue` 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 `ICorDebugValue` 개체 값을 나타내는 공용 언어 런타임 인터페이스입니다.

## <a name="see-also"></a>참고 항목
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)