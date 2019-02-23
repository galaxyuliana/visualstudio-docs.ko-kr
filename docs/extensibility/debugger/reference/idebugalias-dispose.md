---
title: IDebugAlias::Dispose | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d35b5819aa0354581721f02a931aa7bdf679b70d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714961"
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
제거에 대 한이 별칭을 표시합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Dispose();
```

```csharp
int Dispose();
```

#### <a name="parameters"></a>매개 변수
 없음

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 이 메서드가 호출 되 면 별칭 더 이상 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)