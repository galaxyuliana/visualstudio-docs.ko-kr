---
title: GUID_ARRAY | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96313333c330bff1a278a81e1276f8bcd2799e21
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017879"
---
# <a name="guidarray"></a>GUID_ARRAY
사용할 디버그 엔진에 대 한 고유 식별자의 배열을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct tagGUID_ARRAY  
{  
   DWORD dwCount;  
   GUID *Members;  
} GUID_ARRAY;  
```  
  
```csharp  
public struct GUID_ARRAY  
{  
   public uint dwCount;  
   public Guid Members;  
}  
```  
  
## <a name="terms"></a>용어  
 dwCount  
 배열에 있는 고유 식별자의 수입니다.  
  
 멤버  
 고유 식별자가 포함 된 배열입니다.  
  
## <a name="remarks"></a>설명  
 이 구조에서 반환 되는 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)