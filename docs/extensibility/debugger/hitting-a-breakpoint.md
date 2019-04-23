---
title: 중단점 적중 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1286af8222703028d5a8a1bd2dbb0d990ca7e30c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041095"
---
# <a name="hit-a-breakpoint"></a>중단점 도달
다음 섹션에서는 디버그 엔진 (DE)를 실행 하거나 단계별로 실행 하는 동안 중단점에 도달 하면 프로세스를 설명 합니다.

## <a name="troubleshoot-a-hit-breakpoint"></a>적중 횟수 중단점 문제 해결

1. DE 보냅니다는 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 인터페이스는 **EVENT_SYNC_STOP**합니다.

2. 세션 디버그 관리자 (SDM) 호출 [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 적중 된 중단점을 가져오려고 합니다.

## <a name="see-also"></a>참고자료
- [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)