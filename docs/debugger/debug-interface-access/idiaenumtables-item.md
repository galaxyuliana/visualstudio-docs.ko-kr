---
title: 'Idiaenumtables:: Item | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03931580f774c29a67771d2251b51825242535c9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623556"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
인덱스 또는 이름을 사용 하 여 테이블을 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT Item ( 
   VARIANT     index,
   IDiaTable** table
);
```

#### <a name="parameters"></a>매개 변수
 `index`

[in] 인덱스 또는 이름 합니다 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 검색 합니다. 0에서 범위에 있어야는 정수 변형을 사용 하는 경우 `count`-1로, 여기서 `count` 에서 반환 되는 합니다 [idiaenumtables:: Get_count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) 메서드.

 `table`

[out] 반환 된 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 원하는 테이블을 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>주의
 문자열 변형 지정 된 경우 문자열 특정 테이블을 이름입니다. 이름에 정의 된 대로 테이블 이름 중 하나 여야 합니다 [상수 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)합니다.

## <a name="example"></a>예제

```C++
VARIANT var;
var.vt = VT_BSTR;
var.bstrVal = SysAllocString(DiaTable_Symbols );
IDiaTable* pTable;
pEnumTables->Item( var, &pTable );
```

## <a name="see-also"></a>참고 항목
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaEnumTables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)
- [상수(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)