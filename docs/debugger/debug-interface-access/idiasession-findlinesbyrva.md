---
title: IDiaSession::findLinesByRVA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByRVA method
ms.assetid: 06f53b0b-b5b4-42cf-9252-dcee0dbe2d71
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e976fa3172b4f7d3967657b0ac8252d2db93dfb2
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227185"
---
# <a name="idiasessionfindlinesbyrva"></a>IDiaSession::findLinesByRVA
지정 된 상대 가상 주소 RVA ()를 포함 하는 지정 된 compiland에서 줄을 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT findLinesByRVA ( 
    DWORD                 rva,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>매개 변수
`rva`  
[in] RVA로 주소를 지정합니다.

`length`  
[in] 이 쿼리를 처리 하기 위해 주소 범위의 바이트 수를 지정 합니다.

`ppResult`  
[out] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 모든 줄의 목록을 포함 하는 개체 번호 규정 하는 지정된 된 주소 범위입니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="example"></a>예
이 예제에서는 함수의 상대 가상 주소 및 길이 사용 하 여 지정된 된 함수에 포함 된 모든 줄 번호를 가져오는 함수를 보여 줍니다.

```C++
IDiaEnumLineNumbers* GetLineNumbersByRVA(IDiaSymbol *pFunc, IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    DWORD                rva;
    ULONGLONG            length;

    if (pFunc->get_relativeVirtualAddress ( &rva ) == S_OK)
    {
        pFunc->get_length ( &length );
        pSession->findLinesByRVA( rva, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>참고 항목
[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
[IDiaSession](../../debugger/debug-interface-access/idiasession.md)
