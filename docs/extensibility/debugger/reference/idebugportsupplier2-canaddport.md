---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 650b65e043ca16a5aa73a298025819f2fe6802f6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942388"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
포트 공급자가 새 포트를 추가할 수 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>반환 값  
 포트를 추가할 수 있습니다 하는 경우 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 나타내는 포트 없음이 포트 공급자에 추가할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 호출 하기 전에이 메서드를 호출 합니다 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 메서드 하므로 두 번째 방법을 추가 하는 시간이 많이 걸리는 작업 수 뿐만 아니라 포트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)