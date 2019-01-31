---
title: 'Idiasymbol:: Get_virtualaddress | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualAddress method
ms.assetid: dc20c7c0-15a6-4b78-a5c9-2e0b94cac522
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f7db826adb5d88e1f64adde7c87e34047b3c9c6d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54921160"
---
# <a name="idiasymbolgetvirtualaddress"></a>IDiaSymbol::get_virtualAddress
가상 주소 (VA) 위치를 검색 합니다. 사용 시기를 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 로 설정 된 `LocIsStatic`합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 가상 주소의 위치를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)