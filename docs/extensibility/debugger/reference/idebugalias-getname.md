---
title: IDebugAlias::GetName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetName
helpviewer_keywords:
- IDebugAlias::GetName method
ms.assetid: ac2d8891-56b5-40ef-9866-ed74f18bb043
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5858c5b559720486c24bf3fbc7562a13b9fb8372
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683885"
---
# <a name="idebugaliasgetname"></a>IDebugAlias::GetName
이 별칭의 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetName(
   BSTR* pbstrName
);
```

```csharp
int GetName(
   out string pbstrName
);
```

#### <a name="parameters"></a>매개 변수
 `pbstrName`

 [out] 별칭의 이름입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="see-also"></a>참고 항목
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)