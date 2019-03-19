---
title: IDebugApplication110 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110 Interface
ms.assetid: ae943133-eb65-4ddc-a29f-9280a82dd8d6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c040df103bac464e4f440f23674da966063f0ae
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149671"
---
# <a name="idebugapplication110-interface"></a>IDebugApplication110 인터페이스
합니다 `IDebugApplication110` 인터페이스의 기능을 확장 합니다 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)합니다. 구현에서 QueryInterface를 호출 하 여이 인터페이스의 인스턴스를 가져올 수 있습니다 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)합니다.  
  
> [!IMPORTANT]
>  이 인터페이스는 PDM v11.0 이상에 의해 구현됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 `IDebugApplication110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugApplication110::SynchronousCallInMainThread](../../winscript/reference/idebugapplication110-synchronouscallinmainthread.md)|주 스레드에서 동기 호출을 수행 합니다.|  
|[IDebugApplication110::AsynchronousCallInMainThread](../../winscript/reference/idebugapplication110-asynchronouscallinmainthread.md)|주 스레드에 대 한 비동기 호출을 만듭니다.|  
|[IDebugApplication110::CallableWaitForHandles](../../winscript/reference/idebugapplication110-callablewaitforhandles.md)|신호를 받을 수 있도록 하는 동안 지정 된 핸들에 대 한 대기 크로스 스레드 호출이이 스레드를 게시 합니다. 디버거 스레드에서이 메서드를 호출 해야 합니다.|