---
title: IActiveScriptStats::GetStatEx | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.GetStatEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStatEx
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f1585e335fac0072eba48494bf8c27736a47f41
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149171"
---
# <a name="iactivescriptstatsgetstatex"></a>IActiveScriptStats::GetStatEx
사용자 지정 스크립트 통계를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] 반환할 통계를 지정 합니다. 의미 체계에 따라 특정 통계의 GUID가 완전히 정의 하는 엔진입니다.  
  
 `pluHi`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 상위 32 비트입니다.  
  
 `pluLo`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 하위 32 비트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 구현 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용자 지정 호스트에 의미 있는 통계를 반환 하는 사용자 지정 스크립트 엔진을 수 있습니다.  
  
> [!NOTE]
>  이 메서드가 현재 구현 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats 인터페이스](../../winscript/reference/iactivescriptstats-interface.md)