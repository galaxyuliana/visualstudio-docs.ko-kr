---
title: IDiaSymbol::get_isOptimizedAway | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c18b1e38-b152-4a13-aba0-59faded5b2e6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0f8910d35106574912e4a01f7995bfe0f503e3f
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "62836240"
---
# <a name="idiasymbolgetisoptimizedaway"></a>IDiaSymbol::get_isOptimizedAway
변수의 지금 최적화 되었는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_isOptimizedAway(
   BOOL* pRetVal);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 에 대 한 포인터를 `BOOL` 변수의 지금 최적화 되었는지 여부를 지정 하는 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

## <a name="see-also"></a>관련 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)