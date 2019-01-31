---
title: 'Idiastackframe:: Get_cplusplusexceptionhandling | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_cplusplusExceptionHandling method
ms.assetid: f2631820-c986-40ca-b61e-230d7a9c426c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a342fc0c6b63cd518a41210f46dc8c893f36b2eb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54938291"
---
# <a name="idiastackframegetcplusplusexceptionhandling"></a>IDiaStackFrame::get_cplusplusExceptionHandling
C + + 예외 처리에 적용 되는 경우를 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_cplusplusExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 이 프레임에 적용 되는 c + + 예외 처리 하는 경우는 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 속성이 지원 되지 않는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>주의  
 C + + 예외 처리 구조화 된 동일 또는 시스템 예외 처리 아닙니다.  
  
 호출을 확인 하려면 구성 하는 경우 예외 처리가 적용 되는 [IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)