---
title: 'Idiaenumsectioncontribs:: Skip | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c90c2148fc5a563fef8946bd39acf4603d7d09f6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601142"
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
열거형 시퀀스에서 섹션 작성 글의 지정된 된 수를 건너뜁니다.

## <a name="syntax"></a>구문

```C++
HRESULT Skip( 
   ULONG celt
);
```

#### <a name="parameters"></a>매개 변수
 `celt`

[in] 건너뛸 열거형 시퀀스에서 섹션 작성 글의 수입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 없습니다 자세한 섹션 작성 글을 건너뛸 경우.

## <a name="see-also"></a>참고 항목
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)