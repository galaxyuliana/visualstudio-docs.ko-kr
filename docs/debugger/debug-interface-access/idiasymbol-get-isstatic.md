---
title: 'Idiasymbol:: Get_isstatic | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isStatic method
ms.assetid: 3be5fe1b-46e8-4b07-90d8-4929dbbe7ff7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50c19104d0597c9aa178569d0d103bb3e57f18ed
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64813377"
---
# <a name="idiasymbolgetisstatic"></a>IDiaSymbol::get_isStatic
함수 또는 썽크 계층에 표시 되었는지 여부를 정적으로 지정 하는 플래그를 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_isStatic(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>매개 변수
 `pFlag`

[out] 반환 `TRUE` 함수 또는 썽크 계층으로 정적이 고 그렇지 않으면 표시 되었으면, 반환 `FALSE`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="requirements"></a>요구 사항

|요구 사항|Description|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v8.0|

## <a name="see-also"></a>관련 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)