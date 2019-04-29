---
title: IDebugPortNotify2::RemoveProgramNode | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortNotify2::RemoveProgramNode
helpviewer_keywords:
- IDebugPortNotify2::RemoveProgramNode
ms.assetid: 3668157b-66d2-416e-a359-fc04dcd18a48
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c09c7ccfcfee13f667091e96a638c17be2c9616d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871658"
---
# <a name="idebugportnotify2removeprogramnode"></a>IDebugPortNotify2::RemoveProgramNode
실행 되 고 포트에서 디버깅할 수 있는 프로그램을 등록 취소 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT RemoveProgramNode( 
   IDebugProgramNode2* pProgramNode
);
```

```csharp
int RemoveProgramNode( 
   IDebugProgramNode2 pProgramNode
);
```

#### <a name="parameters"></a>매개 변수
 `pProgramNode`

 [in] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 등록을 취소할 프로그램을 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드를 호출 하 여 추가 된 프로그램 노드를 제거 합니다 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
- [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)