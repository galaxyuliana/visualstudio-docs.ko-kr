---
title: 중단점 삭제 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9a70cfe5b728cc9af019752bd0c9c9d2f5105043
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981967"
---
# <a name="deleting-a-breakpoint"></a>중단점 삭제
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음은 보류 중인 중단점을 삭제 하는 경우 프로세스.  
  
## <a name="deletion-process"></a>삭제 프로세스  
 세션 디버그 관리자 (SDM) 호출을 [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) 보류 중인 중단점 및 바인딩된 모든 중단점을 제거 하는 방법에서 바인딩됩니다.  
  
> [!NOTE]
>  호출 하 여 단일 바인딩된 중단점을 삭제할 수도 있습니다 [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)
