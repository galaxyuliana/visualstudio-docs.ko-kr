---
title: 'Idiasymbol:: Get_callingconvention | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_callingConvention method
ms.assetid: 355d3877-b6b6-45fd-a1d8-baed428d8f96
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: aaf71c7b04229fd8c7b08bb8d24212c15f6f5724
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58982807"
---
# <a name="idiasymbolgetcallingconvention"></a>IDiaSymbol::get_callingConvention
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

호출 규칙을 메서드의 표시기를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_callingConvention (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 합니다 [CV_call_e 열거형](../../debugger/debug-interface-access/cv-call-e.md) 메서드를 지정 하는 열거형의 호출 규칙입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CV_call_e 열거형](../../debugger/debug-interface-access/cv-call-e.md)
