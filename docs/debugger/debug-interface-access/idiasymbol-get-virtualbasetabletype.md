---
title: 'Idiasymbol:: Get_virtualbasetabletype | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualBaseTableType method
ms.assetid: e0581c4f-0343-49b5-9754-a48477460e9f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3be75efa175e281378e722e3d10a36cf4b612f7e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636699"
---
# <a name="idiasymbolgetvirtualbasetabletype"></a>IDiaSymbol::get_virtualBaseTableType
가상 기본 테이블 포인터의 형식을 검색합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_virtualBaseTableType(
   IDiaSymbol *pRetVal
};
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`pRetVal`|[out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기본 테이블의 형식을 지정 하는 개체입니다.|

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="remarks"></a>주의
 가상 기본 테이블 대 한 포인터 (`vbtptr`)에 대 한 숨겨진 포인터가 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] vtable 가상 기본 클래스에서 상속을 처리 하는 합니다. `vbtptr` 상속 된 클래스에 따라 다양 한 크기를 가질 수 있습니다.

 이 메서드는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 는 vbtptr의 크기를 결정 하는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v8.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)