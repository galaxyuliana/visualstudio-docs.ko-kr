---
title: IDebugApplicationThreadEvents110::OnThreadRequestComplete | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnThreadRequestComplete
ms.assetid: 7cdd73f3-d78e-4e2f-a204-7a1c45366b87
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3afb36f430d78df4fe99856fd44cb6fda943a9d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160500"
---
# <a name="idebugapplicationthreadevents110onthreadrequestcomplete"></a>IDebugApplicationThreadEvents110::OnThreadRequestComplete
호출 PDM의 스레드를 사용 하 여 스레드를 전환 완료 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThreadEvents110 인터페이스](../../winscript/reference/idebugapplicationthreadevents110-interface.md) 는 PDM v11.0에 의해 구현 된 이상. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnThreadRequestComplete( void );  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThreadEvents110 인터페이스](../../winscript/reference/idebugapplicationthreadevents110-interface.md)