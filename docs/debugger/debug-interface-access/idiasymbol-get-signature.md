---
title: 'Idiasymbol:: Get_signature | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_signature method
ms.assetid: 0efefa39-49a5-4282-9d41-e50832d927e0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 212e05a60dd85348dcb80a12d9c6b06efa2a9f7a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54982964"
---
# <a name="idiasymbolgetsignature"></a>IDiaSymbol::get_signature
기호 서명 값을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_signature (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 기호 서명 값을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)