---
title: 'Idiasymbol:: Get_isnaked | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isNaked method
ms.assetid: b16629dc-8e17-476b-9c7b-58e7277c61ed
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c3b7dcdfe5f101a3b832a550c53d02007d9afba1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56605785"
---
# <a name="idiasymbolgetisnaked"></a>IDiaSymbol::get_isNaked
함수에 있는지 여부를 지정 하는 플래그를 검색 합니다 [naked](/cpp/cpp/naked-cpp) 특성 (즉, 함수에 프롤로그 또는 에필로그 코드 컴파일러에 의해 추가).

## <a name="syntax"></a>구문

```C++
HRESULT get_isNaked(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>매개 변수
 `pFlag`

[out] 반환 `TRUE` 함수에 있으면 합니다 `naked` 반환이 고, 그렇지 않으면 특성 `FALSE`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v8.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [Naked 함수 호출](/cpp/cpp/naked-function-calls)