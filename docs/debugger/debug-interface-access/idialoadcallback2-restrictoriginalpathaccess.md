---
title: IDiaLoadCallback2::RestrictOriginalPathAccess | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictOriginalPathAccess method
ms.assetid: 31fde3af-2824-4b0f-8d0d-cee6046596f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26539d4217682b4d5357f13e9f9368c81297da78
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839747"
---
# <a name="idialoadcallback2restrictoriginalpathaccess"></a>IDiaLoadCallback2::RestrictOriginalPathAccess
원래 디버그 디렉터리에.pdb 파일을 검색할 수 있는지 확인 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT RestrictOriginalPathAccess ();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이외의 다른 모든 반환 코드 `S_OK` 원래 디버그 디렉터리에.pdb 파일을 찾는 것을 금지 합니다. 원래 디버그 디렉터리가에 디버깅이 설정 된 경우 실행 파일로 컴파일된 기호 파일의 경로입니다. 이 경로가 않습니다 반드시 실행 파일이 있는 경로와 동일 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)