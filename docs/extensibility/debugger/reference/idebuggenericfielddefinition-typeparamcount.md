---
title: IDebugGenericFieldDefinition::TypeParamCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- TypeParamCount
- IDebugGenericFieldDefinition::TypeParamCount
ms.assetid: d41dd5ea-aa25-4bf3-bcfd-e0bf451ead49
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2e6334f727b0c40352b7e6ca9b9a199edd98a502
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690606"
---
# <a name="idebuggenericfielddefinitiontypeparamcount"></a>IDebugGenericFieldDefinition::TypeParamCount
제네릭 field와 연관 된 형식 매개 변수 개수를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT TypeParamCount(
   ULONG32* pcParams
);
```

```csharp
int TypeParamCount(
   ref uint pcParams
);
```

#### <a name="parameters"></a>매개 변수
 `pcParams`

 [out에서] 형식 매개 변수 개수입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 경우 목록\<T >,이 메서드가 1을 반환 합니다. 있으면 목록\<T1, T2 >,이 메서드는 2를 반환 합니다. 이 메서드 형식 매개 변수가 없는 경우 0을 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)