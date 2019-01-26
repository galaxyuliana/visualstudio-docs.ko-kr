---
title: IDebugPortSupplier3::CanPersistPorts | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier3::CanPersistPorts
helpviewer_keywords:
- IDebugPortSupplier3::CanPersistPorts
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 78d66f9d267745c1e39c7fc007680009f8881eb4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54933791"
---
# <a name="idebugportsupplier3canpersistports"></a>IDebugPortSupplier3::CanPersistPorts
이 메서드는 지속할 지 여부를 포트 공급자 수 포트 (디스크에 쓴 후)에서 디버거는 호출 간에 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanPersistPorts();  
```  
  
```csharp  
int CanPersistPorts();  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 `S_OK` 포트를 유지 하는 경우 또는 `S_FALSE` 나타내는 포트를 유지할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 포트 공급자는 포트를 유지할 수 있습니다, 소멸 될 때 사용자에 게 이렇게 하며 다음 다시 한 번 인스턴스화될 때 다시 로드 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)