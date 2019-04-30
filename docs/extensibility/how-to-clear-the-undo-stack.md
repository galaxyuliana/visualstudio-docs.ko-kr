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
ms.openlocfilehash: 1d6e7c2536b7c5556139ce7a9b56756e20fd3648
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62911923"
---
# <a name="how-to-clear-the-undo-stack"></a>방법: 실행 취소 스택을 지웁니다.
아래에 다음 프로시저 실행 취소 스택을 지웁니다. 하는 방법에 설명 합니다.

## <a name="to-clear-the-undo-stack"></a>실행 취소 스택을 지웁니다.

1. 실행 취소 스택을 사용의 선택을 취소 하는 [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom) 메서드. 다음은이 예제입니다.

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
- [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)