---
title: 'Idiasymbol:: Get_virtualbaseoffset | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualBaseOffset method
ms.assetid: 103b034f-36c4-42d5-aa34-1449a1e66d03
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c9ff5e8e65e46f9c42c5ea149a5bc5025b83d82b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63385899"
---
# <a name="idiasymbolgetvirtualbaseoffset"></a>IDiaSymbol::get_virtualBaseOffset
가상 함수는 가상 함수 테이블의 오프셋을 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_virtualBaseOffset ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 가상 함수는 가상 함수 테이블의 오프셋을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)