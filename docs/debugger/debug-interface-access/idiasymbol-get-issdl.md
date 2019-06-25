---
title: IDiaSymbol::get_isSdl | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6aa0e116-da75-4643-a4d7-d8e142231e21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6904fc673462a79578549bcf22c2973a5c10c95c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836437"
---
# <a name="idiasymbolgetissdl"></a>IDiaSymbol::get_isSdl
모듈 /SDL 옵션을 사용 하 여 컴파일 되었는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_isSdl(
   BOOL *pRetVal);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 에 대 한 포인터를 `BOOL` 모듈 /SDL 옵션을 사용 하 여 컴파일 되었는지 여부를 지정 하는 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)