---
title: 중단점 적중 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5ae077b8ccb4ce41f94fbc5e11bfff1f16c826c0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981965"
---
# <a name="hitting-a-breakpoint"></a>중단점 적중
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음 프로세스 디버그 엔진 (DE)를 실행 하거나 단계별로 실행 하는 동안 중단점에 도달 하면 설명 합니다.  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>적중 횟수 중단점 문제 해결  
  
1.  DE 보냅니다는 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 인터페이스는 **EVENT_SYNC_STOP**합니다.  
  
2.  세션 디버그 관리자 (SDM) 호출 [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 적중 된 중단점을 가져오려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)
