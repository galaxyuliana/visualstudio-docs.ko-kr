---
title: IDebugEngine2::RemoveAllSetExceptions | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveAllSetExceptions
helpviewer_keywords:
- IDebugEngine2::RemoveAllSetExceptions
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8f5eb2542fa16d86dd342ae0e2783ac03ca69ee4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703411"
---
# <a name="idebugengine2removeallsetexceptions"></a>IDebugEngine2::RemoveAllSetExceptions
IDE는 특정 런타임 아키텍처 또는 언어에 대해 설정한 예외 목록을 제거 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT RemoveAllSetExceptions( 
   REFGUID guidType
);
```

```csharp
int RemoveAllSetExceptions( 
   ref Guid guidType
);
```

#### <a name="parameters"></a>매개 변수
 `guidType`

 [in] 언어에 대 한 GUID 또는 런타임 아키텍처 관련 된 디버그 엔진에 대 한 GUID입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 방법으로 제거 하는 예외에 대 한 이전 호출에서 설정한 합니다 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 메서드.

 특정 예외를 제거 하려면 다음을 호출 합니다 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)