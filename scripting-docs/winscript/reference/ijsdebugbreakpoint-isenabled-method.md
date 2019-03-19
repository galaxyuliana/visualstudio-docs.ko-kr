---
title: 'Ijsdebugbreakpoint:: Isenabled 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.IsEnabled
apilocation:
- jscript9diag.dll
ms.assetid: 39b63f49-2a0d-41b7-a2ba-75dcb06251a9
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b99df17f73896b4dd04481315b04e1672a56285a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159506"
---
# <a name="ijsdebugbreakpointisenabled-method"></a>IJsDebugBreakPoint::IsEnabled 메서드
중단점을 설정할지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT IsEnabled(  
   BOOL *pIsEnabled  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pIsEnabled`  
 [out] 중단점 활성화 되 면 true를 반환 합니다 그렇지 않으면 false를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 삭제 된 중단점에서 E_UNEXPECTED를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugBreakPoint 인터페이스](../../winscript/reference/ijsdebugbreakpoint-interface.md)