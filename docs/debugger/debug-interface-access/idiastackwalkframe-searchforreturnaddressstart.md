---
title: 'Idiastackwalkframe:: Searchforreturnaddressstart | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a9c1e28c458ad863248235166df03cb2ae4f8a3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931234"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
지정한 스택 프레임이 나 지정된 된 주소 반환 주소를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT searchForReturnAddressStart (   
   IDiaFrameData* frame,  
   ULONGLONG      startAddress,  
   ULONGLONG*     returnAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `frame`  
 [in] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 현재 스택 프레임을 나타내는 개체입니다.  
  
 `startAddress`  
 [in] 검색을 시작 하는 가상 메모리 주소입니다.  
  
 `returnAddress`  
 [out] 가장 가까운 반환 주소를 반환 `startAddress`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)