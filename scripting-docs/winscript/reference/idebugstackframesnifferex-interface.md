---
title: IDebugStackFrameSnifferEx 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrameSnifferEx interface
ms.assetid: fd6cf744-dee7-45f2-9a90-355b90372923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc6e892c00a2d86e784857f08772550897e1ec4e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157141"
---
# <a name="idebugstackframesnifferex-interface"></a>IDebugStackFrameSnifferEx 인터페이스
구성 요소에 의해 알려진 논리 스택 프레임을 열거 하는 방법을 제공 합니다. 스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다. 이 모든 스택 프레임을 찾으려면 인터페이스 프로세스 디버그 관리자에서는 지정 된 스레드와 연결 합니다.  
  
> [!NOTE]
>  이 인터페이스는 관심 스레드 내에서 호출 됩니다. 인터페이스 구현은 현재 스레드를 식별 하 고 적절 한 열거자를 반환 해야 합니다.  
  
 상속 된 메서드 외에도 `IDebugStackFrameSniffer`, `IDebugStackFrameSnifferEx` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|현재 스레드의 스택 프레임의 열거자를 반환합니다.|