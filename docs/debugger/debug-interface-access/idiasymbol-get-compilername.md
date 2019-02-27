---
title: IDiaSymbol::get_compilerName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_compilerName method
ms.assetid: 66eaaf72-68d4-40ee-b132-97bea9fe395c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94a054446332c60236ead4a3f034f6bc001a7feb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621762"
---
# <a name="idiasymbolgetcompilername"></a>IDiaSymbol::get_compilerName
생성 하는 데 사용 하는 컴파일러의 이름을 반환 합니다 [Compiland](../../debugger/debug-interface-access/compiland.md)합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_compilerName (
   BSTR *pName
);
```

#### <a name="parameters"></a>매개 변수
 `pName` 컴파일러의 유니코드 이름이 포함 됩니다 하는 BSTR에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="remarks"></a>주의

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v8.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)