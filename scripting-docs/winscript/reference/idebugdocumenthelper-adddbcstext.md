---
title: 'Idebugdocumenthelper:: Adddbcstext | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDBCSText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDBCSText
ms.assetid: 5e5011b2-bbb4-491b-9a11-eb2846be44aa
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d5de41ff83f3ffd5b208445830862138511ba2b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154795"
---
# <a name="idebugdocumenthelperadddbcstext"></a>IDebugDocumentHelper::AddDBCSText
이 문서의 끝에 DBCS 문자열을 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT AddDBCSText(  
   LPCSTR  pszText  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszText`  
 [in] 텍스트를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|메서드가 문자를 추가할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 생성 `IDebugDocumentTextEvents` 알림.  
  
> [!NOTE]
>  이 메서드가 이후에 호출 하는 경우 `IDebugDocumentHelper::AddDeferredText` 가 호출 된 `E_FAIL` 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)