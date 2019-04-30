---
title: 중단 모드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode
- debugging [Debugging SDK], entering break mode
ms.assetid: e9a8a241-cd21-4d4e-999a-283554c288b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8da96c1df3423665ed223fecdd43007ba5a6e671
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925757"
---
# <a name="enter-break-mode"></a>중단 모드를 입력 합니다.
다음 정보는 함수를 한 단계씩 실행, 실행, 커서에 있는 소스 코드의 줄으로 또는 중단점까지 실행 후 중단점을 발견할 때 발생 하는 프로세스를 설명 합니다.

## <a name="break-mode-process"></a>중단 모드 프로세스

1. 디버그 엔진 (DE)를 보냅니다 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md), 또는 다른 중지 이벤트를 중단 모드로 IDE.

2. SDM를 다음과 같은 스레드에서 호출 스택 정보를 가져옵니다.

    - [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)

    - [IEnumDebugFrameInfo2::GetCount](../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)

    - [IEnumDebugFrameInfo2::Next](../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)

    - [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 소스 코드 정보를 가져오려면

    - [IDebugDocumentContext2::GetName](../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md) 파일 이름을 가져오려면

    - [IDebugDocumentContext2::GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) 문의 범위를 가져오려면

    - [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) 메모리 정보를 가져오려면

## <a name="see-also"></a>참고자료
- [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)