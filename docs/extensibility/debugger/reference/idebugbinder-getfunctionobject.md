---
title: IDebugBinder::GetFunctionObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::GetFunctionObject
helpviewer_keywords:
- IDebugBinder::GetFunctionObject method
ms.assetid: 8fb789df-8f30-420d-8ca5-bb496a6738f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 95c770036f691be5146aac1e64f08a8b8de0122a
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615040"
---
# <a name="idebugbindergetfunctionobject"></a>IDebugBinder::GetFunctionObject
이 메서드를 가져옵니다는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 함수 매개 변수를 만드는 데 사용 되는 개체입니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetFunctionObject( 
   IDebugFunctionObject **ppFunction
);
```

```csharp
int GetFunctionObject(
   out IDebugFunctionObject ppFunction
);
```

## <a name="parameters"></a>매개 변수
`ppFunction`\
[out] 반환 된 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 함수 매개 변수를 만드는 데 사용 되는 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="see-also"></a>참고자료
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)