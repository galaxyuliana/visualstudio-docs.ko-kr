---
title: 중단 모드 단계별 실행 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4aefa1c4b3767ae58cb526c6f5a663350efd3137
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922875"
---
# <a name="stepping-in-break-mode"></a>중단 모드 단계별 실행
다음 섹션에서는 디버거가 중단 모드 이며 코드를 단계별로 실행 해야 하는 경우 발생 하는 프로세스를 설명 합니다.  
  
## <a name="stepping-process"></a>단계별 프로세스  
  
1.  호출 [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) 사용 하 여 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 하 고 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 단계의 실행에 대 한 인수입니다.  
  
2.  단계가 완료 되 면 송신을 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 중지 이벤트입니다.  
  
## <a name="see-also"></a>참고자료  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)