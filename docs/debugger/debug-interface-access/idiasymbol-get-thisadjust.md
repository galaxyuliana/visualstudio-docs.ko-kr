---
title: 'Idiasymbol:: Get_thisadjust | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thisAdjust method
ms.assetid: 56b9a147-e8c0-4d4b-a42a-398214dd5f86
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2dfdfb07f0ea20cf13a56eed7f380e3ec195fe52
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63400378"
---
# <a name="idiasymbolgetthisadjust"></a>IDiaSymbol::get_thisAdjust
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

논리 검색 `this` 조정기 메서드에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_thisAdjust (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 논리적 반환 `this` 조정기 메서드에 대 한 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
> 반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 메서드 자체 해야 진정한을 계산 하는 데 여러 상속 경우도 `this` 값에 대 한 오프셋을 추가 하 여 `this`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
