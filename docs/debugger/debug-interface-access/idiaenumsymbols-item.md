---
title: 'Idiaenumsymbols:: Item | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Item method
ms.assetid: 2bd1ec04-e677-4e32-8e32-33334f1eed77
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91c230f641612c099495c54db67da9c7e755cbdc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607137"
---
# <a name="idiaenumsymbolsitem"></a>IDiaEnumSymbols::Item
인덱스를 사용 하 여 기호를 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT Item ( 
   DWORD        index,
   IDiaSymbol** symbol
);
```

#### <a name="parameters"></a>매개 변수
 인덱스입니다.

[in] 인덱스를 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 검색 된 개체입니다. 인덱스는 0에서 범위 `count`-1로, 여기서 `count` 반환한를 [idiaenumsymbols:: Get_count](../../debugger/debug-interface-access/idiaenumsymbols-get-count.md) 메서드.

 기호

[out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 원하는 기호를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)