---
title: BasicType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7fb6000da7ab5d9ff17f78cacf87608432b839e8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55030936"
---
# <a name="basictype"></a>BasicType
기호 기본 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31,  
   btChar16   = 32,  // char16_t
   btChar32   = 33,  // char32_t
};  
```  
  
## <a name="elements"></a>요소  
 btNoType  
 기본 형식이 지정 되지 않은 합니다.  
  
 btVoid  
 기본 형식은 `void`합니다.  
  
 btChar  
 기본 형식은 `char` (C/c + + 형식).  
  
 btWChar  
 기본 형식은 와이드 (유니코드) 문자 (`WCHAR`).  
  
 btInt  
 기본 형식은 `signed int` (C/c + + 형식).  
  
 btUInt  
 기본 형식은 `unsigned int` (C/c + + 형식).  
  
 btFloat  
 기본 형식은 부동 소수점 숫자로 (`FLOAT`).  
  
 btBCD  
 기본 형식은 이진 코딩 된 10 진수 (`BCD`).  
  
 btBool  
 기본 형식은 부울 (`BOOL`).  
  
 btLong  
 기본 형식은 `long int` (C/c + + 형식).  
  
 btULong  
 기본 형식은 `unsigned long int` (C/c + + 형식).  
  
 btCurrency  
 기본 형식은 통화입니다.  
  
 btDate  
 기본 형식은 날짜/시간 (`DATE`).  
  
 btVariant  
 기본 형식은 변수 형식 구조 (`VARIANT`).  
  
 btComplex  
 기본 형식은 복소수입니다.  
  
 btBit  
 기본 형식은 약간입니다.  
  
 btBSTR  
 기본 형식은 기본 또는 이진 문자열 (`BSTR`).  
  
 btHresult  
 기본 형식은 `HRESULT`합니다.  
  
## <a name="remarks"></a>주의  
 이 열거형의 값에서 반환 되는 [idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)
