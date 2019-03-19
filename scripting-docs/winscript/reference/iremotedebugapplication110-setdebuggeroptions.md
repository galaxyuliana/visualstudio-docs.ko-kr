---
title: IRemoteDebugApplication110::SetDebuggerOptions | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::SetDebuggerOptions
ms.assetid: 58e9fd18-3e0d-47fa-8893-f316146bde84
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511d1f8b25aee4637455e3a5b8946f81f7410d65
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150831"
---
# <a name="iremotedebugapplication110setdebuggeroptions"></a>IRemoteDebugApplication110::SetDebuggerOptions
디버거 옵션을 업데이트 하기 위해 호출 됩니다. 이 메서드가 이후에 호출 되도록 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)합니다. 합니다 [IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md) 메서드 기본 옵션을 자동으로 다시 설정 합니다. 0 (SDO_NONE) 기본 옵션입니다.  
  
> [!IMPORTANT]
>  [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md) 는 PDM v11.0에 의해 구현 된 이상. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDebuggerOptions(        [in] enum SCRIPT_DEBUGGER_OPTIONS mask,        [in] enum SCRIPT_DEBUGGER_OPTIONS value    );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mask`  
 합니다 [SCRIPT_DEBUGGER_OPTIONS 열거형](../../winscript/reference/script-debugger-options-enumeration.md) 마스크입니다.  
  
 `value`  
 합니다 [SCRIPT_DEBUGGER_OPTIONS 열거형](../../winscript/reference/script-debugger-options-enumeration.md) 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 인터페이스](../../winscript/reference/iremotedebugapplication110-interface.md)