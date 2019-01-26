---
title: IDebugModule3::LoadSymbols | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a14406d0aeb58cead006ef9f1d5485a053d4a72c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021064"
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
현재 모듈에 대 한 기호를 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```csharp  
int LoadSymbols();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하는 경우 반환 `S_OK`합니다. 실패 한 경우 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 검색 경로에서 기호 로드 (호출 하 여 변경할 수 있습니다 합니다 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) 메서드).  
  
 이 메서드는 보다 선호 합니다 [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)