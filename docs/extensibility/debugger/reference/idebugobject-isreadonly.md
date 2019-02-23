---
title: IDebugObject::IsReadOnly | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::IsReadOnly
helpviewer_keywords:
- IDebugObject::IsReadOnly method
ms.assetid: c460f772-d08a-4b36-81f3-dff6a51a93fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bef21a491a175e7f1a7f93cd7c8d9d70a5ec6279
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682624"
---
# <a name="idebugobjectisreadonly"></a>IDebugObject::IsReadOnly
이 개체가 읽기 전용인 경우를 결정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsReadOnly( 
   BOOL* pfIsReadOnly
);
```

```csharp
int IsReadOnly(
   out int pfIsReadOnly
);
```

#### <a name="parameters"></a>매개 변수
 `pfIsReadOnly`

 [out] 0이 아닌 값을 반환 합니다 (`TRUE`)이이 개체는 읽기 전용 이면이 고 그렇지 인 경우 0을 반환 합니다 (`FALSE`).

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 읽기 전용 개체를 해당 값을 만든 후 변경할 수 없습니다.

## <a name="see-also"></a>참고 항목
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)