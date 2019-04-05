---
title: 중단 모드 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode
- debugging [Debugging SDK], entering break mode
ms.assetid: e9a8a241-cd21-4d4e-999a-283554c288b1
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6ce6c5ca93e8d75908b55efaaee034ab2df77906
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985841"
---
# <a name="entering-break-mode"></a>중단 모드 적용
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음은 함수를 한 단계씩 실행, 실행, 커서에 있는 소스 코드의 줄으로 또는 중단점까지 실행 후 중단점에 도달할 때 발생 하는 프로세스를 설명 합니다.  
  
## <a name="break-mode-process"></a>중단 모드 프로세스  
  
1.  디버그 엔진 (DE)를 보냅니다 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md), 또는 다른 중지 이벤트를 중단 모드로 IDE.  
  
2.  SDM를 다음과 같은 스레드에서 호출 스택 정보를 가져옵니다.  
  
    -   [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)  
  
    -   [IEnumDebugFrameInfo2::GetCount](../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)  
  
    -   [IEnumDebugFrameInfo2::Next](../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)  
  
    -   [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 소스 코드 정보를 가져오려면  
  
    -   [IDebugDocumentContext2::GetName](../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md) 파일 이름을 가져오려면  
  
    -   [IDebugDocumentContext2::GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) 문의 범위를 가져오려면  
  
    -   [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) 메모리 정보를 가져오려면  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)
