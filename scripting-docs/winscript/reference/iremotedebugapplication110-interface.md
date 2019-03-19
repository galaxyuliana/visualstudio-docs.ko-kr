---
title: IRemoteDebugApplication110 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110 Interface
ms.assetid: 785ab46a-8827-41cb-806a-132e6b2c8f47
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d702699aa2e980c3be9d4d05eef96261a788788
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145098"
---
# <a name="iremotedebugapplication110-interface"></a>IRemoteDebugApplication110 인터페이스
스크립트 디버거에서 호출할 수 있으며 in-process 호출자는 새 기능을 제공 하는 데 사용 합니다.  
  
> [!IMPORTANT]
>  이 인터페이스는 PDM v11.0 이상에 의해 구현됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 `IRemoteDebugApplication110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IRemoteDebugApplication110::SetDebuggerOptions](../../winscript/reference/iremotedebugapplication110-setdebuggeroptions.md)|디버거 옵션을 업데이트 하기 위해 호출 됩니다. 0 (SDO_NONE) 기본 옵션입니다.|  
|[IRemoteDebugApplication110::GetCurrentDebuggerOptions](../../winscript/reference/iremotedebugapplication110-getcurrentdebuggeroptions.md)|현재 사용할 수 있는 옵션 집합을 반환 합니다.|  
|[IRemoteDebugApplication110::GetMainThread](../../winscript/reference/iremotedebugapplication110-getmainthread.md)|SetSite를 호출 하는 호스트에 대 한 주 스레드를 반환 합니다.|