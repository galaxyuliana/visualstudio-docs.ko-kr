---
title: IDebugCoreServer3::DisableAutoAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DisableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::DisableAutoAttach
ms.assetid: 9d860a20-c154-4df4-ba15-636e0fcd42bf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5cb6f819d7e1282b567c90623ce89b09eab2600f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922016"
---
# <a name="idebugcoreserver3disableautoattach"></a>IDebugCoreServer3::DisableAutoAttach
이 서버에 연결 된 모든 디버그 엔진에 대 한 자동 연결을 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT DisableAutoAttach(
   void
);
```

```csharp
int DisableAutoAttach();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)