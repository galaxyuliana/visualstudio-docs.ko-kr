---
title: IDebugProgramEx2::GetProgramNode | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 1545ffbf-1422-4b5d-9bb9-314ba8665041
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0b401d1add5d746bf02139154b4475f8d2eb4c0d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069618"
---
# <a name="idebugprogramex2getprogramnode"></a>IDebugProgramEx2::GetProgramNode
프로그램과 연결 된 프로그램 노드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProgramNode(   
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProgramNode(   
   out IDebugProgramNode2 ppProgramNode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppProgramNode`  
 [out] 반환 된 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 이 프로그램을 사용 하 여 연결 프로그램 노드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)