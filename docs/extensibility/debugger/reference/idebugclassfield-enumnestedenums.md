---
title: IDebugClassField::EnumNestedEnums | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bdfa97ccdbf139ce28ec58c07864551c4e6a7d5a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922644"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
이 클래스의 중첩 된 열거자에 대 한 열거자를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumNestedEnums(
    IEnumDebugFields** ppEnum
);
```

```csharp
int EnumNestedEnums(
    out IEnumDebugFields ppEnum
);
```

#### <a name="parameters"></a>매개 변수
`ppEnum`

 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 중첩 된 열거형의 목록을 나타내는 개체입니다. 중첩 된 열거형에 없는 경우 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
성공 하면 S_OK를 반환 하거나 중첩 된 열거자에 없는 경우 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="remarks"></a>설명
열거형의 각 요소는 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) 중첩된 열거형을 설명 하는 개체입니다.

클래스 내에 선언 된 열거형에는 중첩된 된 열거형으로 간주 됩니다. 예를 들어 다음이 지정될 경우

```
class RootClass {
    enum NestedEnum { EnumValue = 0 }
};
```

`EnumNestedEnums` 메서드는 반환를 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 하나가 포함 된 개체 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) 을 나타내는 개체를 `NestedEnum` 열거형입니다.

## <a name="see-also"></a>참고 항목
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
