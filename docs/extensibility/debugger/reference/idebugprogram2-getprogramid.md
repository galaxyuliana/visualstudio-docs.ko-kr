---
title: IDebugProgram2::GetProgramId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetProgramId
helpviewer_keywords:
- IDebugProgram2::GetProgramId
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a3dfec12193efda49a520a40418b93f2d4cef6b1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712894"
---
# <a name="idebugprogram2getprogramid"></a>IDebugProgram2::GetProgramId
이 프로그램에 대 한 GUID를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetProgramId( 
   GUID* pguidProgramId
);
```

```csharp
int GetProgramId( 
   out Guid pguidProgramId
);
```

#### <a name="parameters"></a>매개 변수
 `pguidProgramId`

 [out] 반환 된 `GUID` 이 프로그램에 대 한 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 디버그 엔진 (DE)에 전달 된 원래 프로그램 식별자를 반환 해야 합니다 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 또는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드. 따라서 프로그램의 id 간에 디버거 구성 요소입니다.

## <a name="see-also"></a>참고 항목
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)