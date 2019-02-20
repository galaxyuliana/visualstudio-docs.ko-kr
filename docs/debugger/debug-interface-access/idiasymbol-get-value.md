---
title: 'Idiasymbol:: Get_value | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_value method
ms.assetid: 2e40174a-2a61-4e5f-bb32-9e0ceec2178a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1902985a459a867d389fe61740c8d0b8fee8e41b
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227214"
---
# <a name="idiasymbolgetvalue"></a>IDiaSymbol::get_value
상수 값을 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_value (
    VARIANT* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
`pRetVal`  
[out에서] `VARIANT` 개체는 상수 값이 채워집니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="remarks"></a>주의
제공 된 VARIANT는이 메서드에 전달 되기 전에 초기화 되어야 합니다. 자세한 내용은 예제를 참조 하세요.

## <a name="example"></a>예

```C++
void ProcessValue(IDiaSymbol *pSymbol)
{
    VARIANT value;
    value.vt = VT_EMPTY;    // Initialize variant for use.
    if (pSymbol->get_value(&value) == S_OK)
    {
        // Do something with value.
    }
}

//----------------------------------------------------
// Alternate approach
void ProcessValue2(IDiaSymbol *pSymbol)
{
    CComVariant value;
    if (pSymbol->get_value(&value) == S_OK)
    {
        // Do something with value
    }
}
```

## <a name="see-also"></a>참고 항목
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
