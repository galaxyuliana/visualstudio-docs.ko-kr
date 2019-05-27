---
title: IDebugEngine2::RemoveSetException | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 52d2d628f9fcbc2279096a12117951f4c02f8bf4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66207572"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
지정된 된 예외를 제거 하 여 디버그 엔진에서 더 이상 처리 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT RemoveSetException( 
   EXCEPTION_INFO* pException
);
```

```csharp
int RemoveSetException( 
   EXCEPTION_INFO[] pException
);
```

## <a name="parameters"></a>매개 변수
`pException`\
[in] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 제거할 예외를 설명 하는 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 제거 되는 예외 설정 되어 있어야 이전에 대 한 이전 호출에서 합니다 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 메서드.

 모든 집합 예외를 한 번에 제거를 호출 합니다 [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md) 메서드.

## <a name="see-also"></a>참고자료
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)