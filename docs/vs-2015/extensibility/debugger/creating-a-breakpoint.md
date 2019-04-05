---
title: 중단점 만들기 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, creating
- debugging [Debugging SDK], creating breakpoints
ms.assetid: 6f9f87bb-192e-45e0-9a7a-ffe729e87f7d
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 078b0a46662930f2a8624c1b0d10510728a811d6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985986"
---
# <a name="creating-a-breakpoint"></a>중단점 만들기
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음 중단점을 만드는 과정을 설명 합니다.  
  
## <a name="methods-in-breakpoint-creation"></a>중단점을 만드는 방법  
 중단점을 바인딩할 필요한 모듈 로드 되 면 세션 디버그 관리자 (SDM) 다음 메서드를 호출 합니다.  
  
1.  [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)  
  
2.  [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)  
  
3.  [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)  
  
    > [!NOTE]
    >  **CanBind** 사용자 중단점 창에서 중단점을가 하는 경우에 호출 됩니다.  
  
4.  [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)  
  
5.  [IDebugPendingBreakpoint2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)
