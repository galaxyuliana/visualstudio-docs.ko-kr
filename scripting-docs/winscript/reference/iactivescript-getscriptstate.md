---
title: IActiveScript::GetScriptState | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptState
ms.assetid: 59837f7c-755d-45c4-8194-bd57638fe2e1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f9f3bedee9af9ae3cb145108d801f252267d5d2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58156985"
---
# <a name="iactivescriptgetscriptstate"></a>IActiveScript::GetScriptState
스크립팅 엔진의 현재 상태를 검색합니다. 호스트 개체 또는 기본이 아닌 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetScriptState(  
    SCRIPTSTATE *pss  // address of structure for state information  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pss`  
 [out] 에 정의 된 값을 받을 변수의 주소는 [SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md) 열거형입니다. 값은 호출 스레드와 연결 된 스크립팅 엔진의 현재 상태를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_POINTER` 잘못 된 포인터를 지정 된 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)