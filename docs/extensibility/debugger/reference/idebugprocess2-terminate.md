---
title: IDebugProcess2::Terminate | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::Terminate
helpviewer_keywords:
- IDebugProcess2::Terminate
ms.assetid: 5e6bf373-0fe9-4321-b04a-473a65f664d9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51a38055edaa899adaa08581a9d7bfb01e3196ce
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918840"
---
# <a name="idebugprocess2terminate"></a>IDebugProcess2::Terminate
프로세스를 종료합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 프로세스 종료 되 면 해당 프로세스 내에서 모든 프로그램 종료 됩니다. 자세한 코드를 실행할 수는 없음.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)