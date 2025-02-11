---
title: 'Idiasymbol:: Get_addressoffset | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8fc13197f668f7e046ec8ffc40da246c04449e94
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64825110"
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
주소 위치 오프셋된 부분을 검색합니다. 사용 시기를 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 로 설정 된 `LocIsStatic`합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_addressOffset ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 주소 위치 오프셋된 부분을 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.

## <a name="remarks"></a>설명
 외부 DLL에 정적 멤버에 대 한 멤버의 가상 주소를 얻는 방법에이 메서드를 사용이 메서드에서 반환 되는 오프셋 0 일 수 있습니다. 가상 주소는 유효 경우에만 합니다 [idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) 에서 메서드를 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 인터페이스가 DLL의 로드 주소를 지정 하는 0이 아닌 매개 변수를 사용 하 여 호출 되었습니다.

 주소의 구역을 부분을 가져오려면 호출 합니다 [idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md) 메서드.

## <a name="requirements"></a>요구 사항

|요구 사항|Description|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v7.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
- [IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)
- [IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)