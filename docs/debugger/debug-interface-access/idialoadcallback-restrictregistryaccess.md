---
title: IDiaLoadCallback::RestrictRegistryAccess | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::RestrictRegistryAccess method
ms.assetid: de4760c3-a746-4bab-8065-1388fed31b67
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25e6397b65c717be65a9a707dd0a53fc70321acb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828491"
---
# <a name="idialoadcallbackrestrictregistryaccess"></a>IDiaLoadCallback::RestrictRegistryAccess
레지스트리 쿼리 기호 검색 경로 찾을 수 하는 경우를 결정 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT RestrictRegistryAccess();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이외의 다른 모든 반환 코드 `S_OK` 기호 검색 경로 대 한 레지스트리를 쿼리하여 방지 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)