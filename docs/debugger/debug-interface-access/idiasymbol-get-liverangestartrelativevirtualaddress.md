---
title: IDiaSymbol::get_liveRangeStartRelativeVirtualAddress | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_liveRangeStartRelativeVirtualAddress
ms.assetid: 1da52539-9872-4c20-8eaa-74b6cb5f3b02
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 338775a2c36415d471d0d59176ce38f6df1827bb
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64806870"
---
# <a name="idiasymbolgetliverangestartrelativevirtualaddress"></a>IDiaSymbol::get_liveRangeStartRelativeVirtualAddress
로컬 기호 유효 주소 범위의 시작 부분을 반환 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_liveRangeStartRelativeVirtualAddress ( 
   DWORD* address
);
```

#### <a name="parameters"></a>매개 변수
 `address`

[out] 주소 범위의 시작 날짜를 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 하는 상대 가상 주소에는 기호가 유효한 범위의 시작입니다.

> [!NOTE]
> 반환 된 오류 코드 기호 라이브 범위 정보가 없는 것을 의미 합니다.

## <a name="remarks"></a>설명

## <a name="requirements"></a>요구 사항
 헤더: Dia2.h

 라이브러리: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)