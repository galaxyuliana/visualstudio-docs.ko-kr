---
title: IDebugModOpt | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3e9a883c99bb41decbe0bbb53d2a4c484e021c07
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929298"
---
# <a name="idebugmodopt"></a>IDebugModOpt
디버그 선택적 한정자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 가져온를 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 클래스 또는 메서드를 나타내는 개체입니다.  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|선택적 한정자의 목록을 검색합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll