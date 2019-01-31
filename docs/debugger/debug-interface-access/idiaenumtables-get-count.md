---
title: 'Idiaenumtables:: Get_count | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::get_Count method
ms.assetid: 30fa316b-a746-4028-acae-4efcd2066f38
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f92c860cf0b9d99f5fd4b3f08516afb5ddb0373e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960433"
---
# <a name="idiaenumtablesgetcount"></a>IDiaEnumTables::get_Count
테이블을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_Count (    LONG* pRetVal  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 테이블의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)