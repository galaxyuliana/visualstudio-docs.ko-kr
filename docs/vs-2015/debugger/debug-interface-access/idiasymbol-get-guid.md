---
title: IDiaSymbol::get_guid | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_guid method
ms.assetid: c02a6c92-f406-4646-82e7-3cd005af900e
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eee39447c0bb30a0a51d3b92a4afdbc0ed5d07b5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972551"
---
# <a name="idiasymbolgetguid"></a>IDiaSymbol::get_guid
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

기호 전역적으로 고유 식별자 (GUID)를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_guid (   
   GUID* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 기호 GUID를 반환합니다.  
  
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
