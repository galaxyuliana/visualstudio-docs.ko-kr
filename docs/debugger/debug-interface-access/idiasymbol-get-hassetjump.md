---
title: IDiaSymbol::get_hasSetJump | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasSetJump method
ms.assetid: 22656206-dccf-40ed-b179-fc016d1b262a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82ada6ac52a9eacbd8ec0dee3940a9231564d79a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639364"
---
# <a name="idiasymbolgethassetjump"></a>IDiaSymbol::get_hasSetJump
함수를 사용 하는 포함 되는지 여부를 지정 하는 플래그를 검색 합니다 [setjmp](/cpp/c-runtime-library/reference/setjmp) 명령 (와 연결를 [longjmp](/cpp/c-runtime-library/reference/longjmp) 명령을 이러한 지역은 C 스타일에 대 한 메서드의 예외 처리).

## <a name="syntax"></a>구문

```C++
HRESULT get_hasSetJump(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>매개 변수
 `pFlag`

[out] 반환 `TRUE` 함수를 포함 하는 경우는 `setjmp` 명령, 그렇지 않으면 `FALSE`합니다.

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
- [IDiaSymbol::get_hasLongJump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)
- [longjmp](/cpp/c-runtime-library/reference/longjmp)
- [setjmp](/cpp/c-runtime-library/reference/setjmp)