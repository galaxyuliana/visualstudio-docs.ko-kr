---
title: 'Idiasymbol:: Get_issafebuffers | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isSafeBuffers method
ms.assetid: f29e373d-e7bb-4181-ab9f-bf708d401d83
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f5dd923b9f7244bb42fdf8defb70b8ed5dc82ed0
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64825505"
---
# <a name="idiasymbolgetissafebuffers"></a>IDiaSymbol::get_isSafeBuffers
안전한 버퍼에 대 한 전처리기 지시문 사용 되는지 여부를 지정 하는 플래그를 검색 합니다. 사용 시기를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 로 설정 된 `SymTagFunction`합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_isSafeBuffers( 
   BOOL* pRetVal)
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 반환 `TRUE` 포인터를 안전 하 게 버퍼에 대 한 전처리기 지시문을 사용 하는 경우이 고, 그렇지 반환 `FALSE`합니다.

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
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [strict_gs_check](/cpp/preprocessor/strict-gs-check)