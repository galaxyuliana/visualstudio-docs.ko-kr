---
title: IDiaSymbol::get_isPointerToMemberFunction | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa9b5599-9602-41be-ab50-d84b90bee72f
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 610b2d93814af81995787879008e52059bb3567a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58984004"
---
# <a name="idiasymbolgetispointertomemberfunction"></a>IDiaSymbol::get_isPointerToMemberFunction
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 기호는 멤버 함수에 대 한 포인터 인지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT get_isPointerToMemberFunction(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 에 대 한 포인터를 `BOOL` 이 기호는 멤버 함수에 대 한 포인터 인지 여부를 지정 하는 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
