---
title: IDiaSymbol::get_isAcceleratorStubFunction | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b2c11cc560be00bd51f8c5ebb35803240c5fbe8e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925333"
---
# <a name="idiasymbolgetisacceleratorstubfunction"></a>IDiaSymbol::get_isAcceleratorStubFunction
기호에 해당 하는 액셀러레이터 키에 대 한 컴파일된 셰이더에 대 한 최상위 함수 기호에 해당 하는지 여부를 나타냅니다는 `parallel_for_each` 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_isAcceleratorStubFunction(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 에 대 한 포인터를 `BOOL` 기호에 해당 하는 액셀러레이터 키에 대 한 컴파일된 셰이더에 대 한 최상위 함수 기호에 해당 하는지 여부를 나타내는 `parallel_for_each` 호출 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)