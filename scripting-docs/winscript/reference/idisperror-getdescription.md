---
title: IDispError::GetDescription | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetDescription
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetDescription
ms.assetid: 04deaea6-0265-4e34-952e-634edba0e923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aff28f0f552bcad6792e4d252a92e45e9a6fd38c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146697"
---
# <a name="idisperrorgetdescription"></a>IDispError::GetDescription
오류에 대 한 텍스트 설명을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetDescription(  
   BSTR*  pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrDescription`  
 [out] 오류에 대 한 간략 한 설명이 포함 된 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 에 전달 된 로캘 식별자 (LCID) 하 여 지정 된 언어로 된 텍스트가 반환 됩니다 `IDispatchEx::InvokeEx` 오류가 발생 하는 메서드에 대 한 합니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)