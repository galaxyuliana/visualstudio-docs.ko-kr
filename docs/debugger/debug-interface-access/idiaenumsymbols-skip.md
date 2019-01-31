---
title: 'Idiaenumsymbols:: Skip | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Skip method
ms.assetid: e601fbc9-b10b-41c7-8180-959e57efabe8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0168c3f58cf9bd701f0cc34edf77673c70e66222
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021444"
---
# <a name="idiaenumsymbolsskip"></a>IDiaEnumSymbols::Skip
열거형 시퀀스에서 기호를 지정 된 수를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 건너뛸 열거형 시퀀스에서 기호 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 건너뛸 자세한 기호가 없는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)