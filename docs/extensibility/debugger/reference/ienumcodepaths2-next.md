---
title: IEnumCodePaths2::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2::Next
helpviewer_keywords:
- IEnumCodePaths2::Next
ms.assetid: c7a8fe97-2abc-4cee-8aef-64f1daa93b5c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fda34e457d13d2b5549a20611fdc68830fe19803
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203646"
---
# <a name="ienumcodepaths2next"></a>IEnumCodePaths2::Next
열거형에서 다음 요소 집합을 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Next(
   ULONG       celt,
   CODE_PATH** rgelt,
   ULONG*      pceltFetched
);
```

```csharp
int Next(
   uint        celt,
   CODE_PATH[] rgelt,
   ref uint    pceltFetched
);
```

## <a name="parameters"></a>매개 변수
`celt`\
[in] 검색할 요소의 수입니다. 또한 최대 크기를 지정 된 `rgelt` 배열입니다.

`rgelt`\
[out에서] 배열을 [CODE_PATH](../../../extensibility/debugger/reference/code-path.md) 채울 요소입니다.

`pceltFetched`\
[out] 에 실제로 반환 된 요소의 수를 반환 합니다. `rgelt`합니다.

## <a name="return-value"></a>반환 값
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 요소의 요청 된 수보다 적은; 반환 될 수 있으면이 고, 그렇지 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)
- [CODE_PATH](../../../extensibility/debugger/reference/code-path.md)