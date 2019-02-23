---
title: IDebugModule3::IsUserCode | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::IsUserCode
helpviewer_keywords:
- IDebugModule3::IsUserCode
ms.assetid: 77022946-bb8b-4114-aa81-614df6e54b13
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 39bbef1e8b831473b196d0609459b80a05e5fc2c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718497"
---
# <a name="idebugmodule3isusercode"></a>IDebugModule3::IsUserCode
모듈이 나타내는 사용자 코드 여부에 대 한 정보를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsUserCode(
   BOOL* pfUser
);
```

```csharp
int IsUserCode(
   out int pfUser
);
```

#### <a name="parameters"></a>매개 변수
 `pfUser`

 [out] 0이 아닌 값 (`TRUE`) 모듈에서 사용자 코드를 나타내는 경우에 0 (`FALSE`) 그렇지 않은 경우.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)