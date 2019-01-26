---
title: IDebugPortEx2::GetPortProcessId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1a9cb6a85cd23f0859c8f9ce0aff8c9ef21bf80
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941758"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
포트의 프로세스 ID를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwProcessId`  
 [out] 포트의 실제 프로세스 ID를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 Win32 런타임에서 예를 들어, 일반적으로 호출 Win32 함수 `GetCurrentProcessId` 실제 프로세스 ID를 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)