---
title: 'Idiasymbol:: Get_farreturn | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_farReturn method
ms.assetid: 141df0e9-f4d9-4330-a043-5d9ea865257f
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0feaf83903f2d58a9e7e12f2ff7517c677b96264
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58986494"
---
# <a name="idiasymbolgetfarreturn"></a>IDiaSymbol::get_farReturn
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

함수는 훨씬 반환 포함 되는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_farReturn(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [in] 반환 `TRUE` 함수에서는 지금까지 반환 하는 경우는 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
