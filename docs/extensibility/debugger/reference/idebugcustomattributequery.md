---
title: IDebugCustomAttributeQuery | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f035441a05f711438fd19eaa54e6c6b2a3aab7a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997938"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
메서드 또는 형식에 사용자 지정 특성에 대 한 쿼리를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|이름이 지정 된 사용자 지정 특성을 검색 합니다.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|지정 된 결정 사용자 지정 특성이 정의 되어 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll