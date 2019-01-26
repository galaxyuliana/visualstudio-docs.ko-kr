---
title: 실행 기반 첨부 파일 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa0f03c37b92366e9872cbd170605a385aabdd1a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975857"
---
# <a name="launch-based-attachment"></a>실행 기반 첨부 파일
프로그램 실행 기반 첨부 파일은 자동입니다. 프로그램을 호스트 하는 프로세스는 SDM에서 시작 되 면 실행 기반 첨부 파일의 수동 첨부 방법을 비슷한 경로 따릅니다. 정보를 참조 하세요 [프로그램을 연결할](../../extensibility/debugger/attaching-to-the-program.md)합니다.  
  
## <a name="the-attaching-process"></a>연결 프로세스  
 주요 차이점은 이벤트의 시퀀스를 **연결** 를 다음과 같이 호출 합니다.  
  
1.  보내기는 **IDebugEngineCreateEvent2** SDM 이벤트 개체입니다. 자세한 내용은 참조 하세요 [이벤트를 보낼](../../extensibility/debugger/sending-events.md)합니다.  
  
2.  호출를 `IDebugProgram2::GetProgramId` 메서드를 **IDebugProgram2** 인터페이스에 전달 합니다 **연결** 메서드.  
  
3.  보내기는 **IDebugProgramCreateEvent2** SDM을 알리는 이벤트 개체는 로컬 **IDebugProgram2** 는 DE에 프로그램을 나타내는 개체를 만든 합니다.  
  
4.  보내기는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) 프로세스 시작에 대해 만든 새 스레드는 SDM을 알리는 이벤트 개체입니다.  
  
## <a name="see-also"></a>참고자료  
 [필요한 이벤트 보내기](../../extensibility/debugger/sending-the-required-events.md)   
 [디버깅할 프로그램 사용 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)