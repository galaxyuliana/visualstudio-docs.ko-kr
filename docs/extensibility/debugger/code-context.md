---
title: 상황에 맞는 코드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 868fa51d24b0ae3206d55ae8364224dead69e7f7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55003372"
---
# <a name="code-context"></a>코드 컨텍스트
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 하는 **코드 컨텍스트**:  
  
-   디버그 엔진 (DE)에 알려진 코드 위치의 추상화를 제공 합니다. 대부분의 런타임 아키텍처에 대 한 현재 코드 컨텍스트를 생각할 수 있습니다 프로그램의 명령 스트림의 주소로 합니다. 여기서 코드 지침 표시 될 수 있습니다, 않던 언어에 대 한 코드 컨텍스트를 다른 방법으로 나타낼 수 있습니다.  
  
-   디버깅할 프로그램의 실행 스트림 내의 현재 위치를 설명 합니다.  
  
-   프로그램이 중단점에서 중지 된 경우에 존재 합니다.  
  
-   에 관련된 문서 컨텍스트가 있습니다.  
  
-   에 의해 구현 되는 [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고자료  
 [문서 컨텍스트](../../extensibility/debugger/document-context.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)