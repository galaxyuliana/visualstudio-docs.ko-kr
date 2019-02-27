---
title: IDiaSymbol::get_liveRangeStartAddressOffset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_liveRangeStartAddressOffset
ms.assetid: f5b28914-0a14-4b22-8259-59d7f97ee610
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 06ef9eb5969b351d49212e9b940988e7ff14c40e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636179"
---
# <a name="idiasymbolgetliverangestartaddressoffset"></a>IDiaSymbol::get_liveRangeStartAddressOffset
로컬 기호의 유효 범위 시작 주소 오프셋된 부분을 반환 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_liveRangeStartAddressOffset ( 
   DWORD* offset
);
```

#### <a name="parameters"></a>매개 변수
 `offset`

[out] 시작 주소 범위의 오프셋된 부분을 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

> [!NOTE]
>  반환 된 오류 코드 기호 라이브 범위 정보가 없는 것을 의미 합니다.

## <a name="remarks"></a>주의
 섹션과 오프셋 하 여 만든 주소가 기호가 유효한 범위의 시작입니다.

 섹션에 대 한 부분 주소를 가져오려면 [IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md)합니다.

## <a name="requirements"></a>요구 사항
 헤더: Dia2.h

 라이브러리: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)