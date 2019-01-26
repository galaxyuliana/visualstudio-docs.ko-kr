---
title: IDebugMessageEvent2::GetMessage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8926406ac47cc19b07192662d9f470c7b3e6fa32
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025282"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
표시할 메시지를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMessage(   
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrMessage,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetMessage(   
   out enum_MESSAGETYPE pMessageType,  
   out string           pbstrMessage,  
   out uint             pdwType,  
   out string           pbstrHelpFileName,  
   out uint             dwHelpId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMessageType`  
 [out] 값을 반환 합니다 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) 메시지의 형식을 설명 하는 열거형입니다.  
  
 `pbstrMessage`  
 [out] 메시지를 반환합니다.  
  
 `pdwType`  
 [out] Win32의 규칙을 사용 하 여 메시지의 형식을 반환 `MessageBox` 함수입니다. 참조 된 [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) 세부 정보에 대 한 함수입니다.  
  
 `pbstrHelpFileName`  
 [out에서] 도움말 파일의 이름을 반환합니다. 도움말 파일이 없는 경우 null (c + +) 또는 빈 값 (C#)를 수 있습니다.  
  
 `pdwHelpId`  
 [out에서] 도움말 식별자를 반환합니다. 있습니다 수이 메시지와 관련 된 도움말이 없습니다 경우에 0입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)   
 [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)