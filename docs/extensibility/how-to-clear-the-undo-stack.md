---
title: '방법: 실행 취소 스택을 지웁니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 71c8e80fceef685b49af53fb5c369500315bbea9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55000170"
---
# <a name="how-to-clear-the-undo-stack"></a>방법: 실행 취소 스택을 지웁니다.
아래에 다음 프로시저 실행 취소 스택을 지웁니다. 하는 방법에 설명 합니다.  
  
## <a name="to-clear-the-undo-stack"></a>실행 취소 스택을 지웁니다.  
  
1.  실행 취소 스택을 사용의 선택을 취소 하는 [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom) 메서드. 다음은이 예제입니다.  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>참고자료  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)