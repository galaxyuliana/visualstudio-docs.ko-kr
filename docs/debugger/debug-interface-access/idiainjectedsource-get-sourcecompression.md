---
title: 'Idiainjectedsource:: Get_sourcecompression | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_sourceCompression method
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db0cb61d0b2836e5ed3cd3549dbc393b222c58d8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939960"
---
# <a name="idiainjectedsourcegetsourcecompression"></a>IDiaInjectedSource::get_sourceCompression
사용 되는 원본 압축 표시기를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_sourceCompression (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 사용 되는 원본 압축 표시기를 반환 합니다. 0 값 압축 하지 않고 소스를 사용 했는지를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>주의  
 이 메서드에서 반환 된 값 사용 된 컴파일러와 관련이 있습니다. 예를 들어, 컴파일러는 실행 길이 인코딩 또는 Huffman 스타일 압축을 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)