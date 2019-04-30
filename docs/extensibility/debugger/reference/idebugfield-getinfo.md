---
title: IDebugField::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96ce3c428785bd6b817cb8ce0f97f14a87180d0c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62873895"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
이 메서드는 필드를 표시할 수 있는 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetInfo( 
   FIELD_INFO_FIELDS dwFields,
   FIELD_INFO* pFieldInfo
);
```

```csharp
int GetInfo(
   enum_FIELD_INFO_FIELDS dwFields,
   FIELD_INFO[] pFieldInfo
);
```

#### <a name="parameters"></a>매개 변수
 `dwFields`

 [in] 조합을 [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) 표시할 정보를 선택 하는 상수입니다. 필드 기호를 나타내는 경우 이것이 일반적으로 기호 이름과 형식입니다.

 `pFieldInfo`

 [out] 제공 된 정보를 반환 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)