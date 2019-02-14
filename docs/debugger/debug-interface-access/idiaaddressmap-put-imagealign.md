---
title: 'Idiaaddressmap:: Put_imagealign | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a78b1d03eddfcedb04966276c889219630c45f83
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54950743"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
이미지 맞춤을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 NewVal  
 [in] 실행 파일에 대 한 새 이미지 맞춤 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>주의  
 이미지 (로드 된 실행 파일)는 지정 된 메모리 경계에 정렬 됩니다. 현재 시스템 아키텍처 및 시간 옵션을 컴파일 및 링크 하 여이 맞춤을 달라질 수 있습니다. 이미지 맞춤 바이트 경계 항상 켜져 있습니다. 다음 이미지 맞춤 값이 유효한 지: 1, 2, 4, 8, 16, 32, 64 바이트 경계입니다.  
  
 현재 이미지 맞춤을 호출 하 여 검색할 수는 [idiaaddressmap:: Get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) 메서드.  
  
> [!NOTE]
>  이미지는이 메서드를 호출할 수에 의해 이미 로드 되었습니다. `put_imageAlign` 메서드는 새 맞춤이 필요 하 고 이미지 이동 되거나 변경 된 경우에 일반적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)