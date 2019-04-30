---
title: IEnumDebugBoundBreakpoints2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugBoundBreakpoints2::Reset
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Reset
ms.assetid: 0f0522a5-6a97-4c4e-859b-cc4476e6c527
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a9cd41a82497f232792148a3096b2296db03c834
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62915159"
---
# <a name="ienumdebugboundbreakpoints2reset"></a>IEnumDebugBoundBreakpoints2::Reset
첫 번째 요소를 열거를 초기화합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드를 호출한 후, 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)