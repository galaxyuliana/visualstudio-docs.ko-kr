---
title: IDebugModOpt::GetModOpts | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c611c55654ee14bc3cda3f27fe20e19188faa71a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017165"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
선택적 한정자의 목록을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModOpts(  
   ULONG  celt,  
   BSTR*  rgelt,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetModOpts(  
   uint         celt,  
   out string[] rgelt,  
   ref uint     pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 반환할 요소 수입니다.  
  
 `rgelt`  
 [out] 옵션이 포함 된 배열을 반환 합니다.  
  
 `pceltFetched`  
 [out에서] 반환 된 요소 수를 `rgelt` 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)