---
title: 'Idiasymbol:: Get_framepointerpresent | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_framePointerPresent method
ms.assetid: d036090a-1651-454d-9130-b798f58ba053
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7914845bccb43ce302665428c824bbf3ebb2c819
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63401957"
---
# <a name="idiasymbolgetframepointerpresent"></a>IDiaSymbol::get_framePointerPresent
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

프레임 포인터가 있는지 여부를 지정 하는 플래그를 검색 합니다. 사용 시기를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 로 설정 된 `SymTagFunction`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_framePointerPresent(   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out]] 반환 `TRUE` 존재 하지 않으면 프레임 포인터 이면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
