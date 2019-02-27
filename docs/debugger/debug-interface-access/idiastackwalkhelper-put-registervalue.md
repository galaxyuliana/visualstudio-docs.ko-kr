---
title: IDiaStackWalkHelper::put_registerValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59d076781e0f67ad9a2f2af02e7dc937042b0e71
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56620397"
---
# <a name="idiastackwalkhelperputregistervalue"></a>IDiaStackWalkHelper::put_registerValue
레지스터의 값을 설정 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT put_registerValue ( 
   DWORD     index,
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>매개 변수
 `index`

[in] 값을 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 쓸 레지스터를 지정 하는 열거형입니다.

 `NewVal`

[in] 새 값을 등록합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>주의
 값의 크기에도 불구 하 고 구현만 무엇입니까 레지스터 일반적으로 보유 저장 해야 합니다. 예를 들어, 8 비트 레지스터를 가장 낮은 8-비트만 지정된 된 값의 저장 해야 합니다.

## <a name="see-also"></a>참고 항목
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)