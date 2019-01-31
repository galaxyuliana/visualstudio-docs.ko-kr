---
title: IDiaSession::findSymbolsForAcceleratorPointerTag | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 95fd5e7a-c637-437e-b369-c864eef733c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14a601143161ed17961ae5efd22cdc14c3fbb923
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924391"
---
# <a name="idiasessionfindsymbolsforacceleratorpointertag"></a>IDiaSession::findSymbolsForAcceleratorPointerTag
부모 Accelerator 스텁 함수에서에서 지정 된 태그 값에 해당 하는 변수에 대 한 기호의 열거형을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findSymbolsForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] 검색할 Accelerator 스텁 함수에 해당 하는 IDiaSymbol 합니다.  
  
 `tagValue`  
 [in] 포인터 태그 값입니다.  
  
 `ppResult`  
 [out] 에 대 한 포인터는 `IDiaEnumSymbols` 결과 사용 하 여 초기화 된 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)