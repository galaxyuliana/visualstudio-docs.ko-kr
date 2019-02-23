---
title: IDebugObject2::GetAlias | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetAlias
helpviewer_keywords:
- IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7d08d9108ed4a433bcbcb17d6d4587532542b303
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719849"
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
있는 경우이 개체와 연결 된 별칭을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetAlias(
   IDebugAlias** ppAlias
);
```

```csharp
int GetAlias(
   out IDebugAlias ppAlias
);
```

#### <a name="parameters"></a>매개 변수
 `ppAlias`

 [out] 반환 된 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 이 개체에 대 한 별칭을 나타내는 개체, 그렇지 않으면 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 에 대 한 호출을 사용 하 여 개체에 대 한 별칭이 만들어집니다 합니다 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)