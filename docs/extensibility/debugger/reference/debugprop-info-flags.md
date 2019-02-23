---
title: DEBUGPROP_INFO_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 131e014e3714df708c5ef1526ecb911531c5a5c3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689111"
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
디버그 속성 개체에 대 한 검색 정보를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_DEBUGPROP_INFO_FLAGS {
    DEBUGPROP_INFO_FULLNAME          = 0x00000001,
    DEBUGPROP_INFO_NAME              = 0x00000002,
    DEBUGPROP_INFO_TYPE              = 0x00000004,
    DEBUGPROP_INFO_VALUE             = 0x00000008,
    DEBUGPROP_INFO_ATTRIB            = 0x00000010,
    DEBUGPROP_INFO_PROP              = 0x00000020,
    DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,
    DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,
    DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,
    DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000
    DEBUGPROP_INFO_NONE              = 0x00000000,
    DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |
                                        DEBUGPROP_INFO_NAME |
                                        DEBUGPROP_INFO_TYPE |
                                        DEBUGPROP_INFO_VALUE,
    DEBUGPROP_INFO_ALL               = 0xffffffff
};
typedef DWORD DEBUGPROP_INFO_FLAGS;
```

```csharp
public enum enum_DEBUGPROP_INFO_FLAGS {
    DEBUGPROP_INFO_FULLNAME          = 0x00000001,
    DEBUGPROP_INFO_NAME              = 0x00000002,
    DEBUGPROP_INFO_TYPE              = 0x00000004,
    DEBUGPROP_INFO_VALUE             = 0x00000008,
    DEBUGPROP_INFO_ATTRIB            = 0x00000010,
    DEBUGPROP_INFO_PROP              = 0x00000020,
    DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,
    DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,
    DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,
    DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000
    DEBUGPROP_INFO_NONE              = 0x00000000,
    DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |
                                        DEBUGPROP_INFO_NAME |
                                        DEBUGPROP_INFO_TYPE |
                                        DEBUGPROP_INFO_VALUE,
    DEBUGPROP_INFO_ALL               = 0xffffffff
};
```

## <a name="members"></a>멤버
DEBUGPROP_INFO_FULLNAME 초기화/사용 된 `bstrFullName` 필드입니다.

DEBUGPROP_INFO_NAME 초기화/사용 된 `bstrName` 필드입니다.

DEBUGPROP_INFO_TYPE 초기화/사용 된 `bstrType` 필드입니다.

DEBUGPROP_INFO_VALUE 초기화/사용 된 `bstrValue` 필드입니다.

DEBUGPROP_INFO_ATTRIB 초기화/사용 된 `dwAttrib` 필드입니다.

DEBUGPROP_INFO_PROP 초기화/사용 된 `pProperty` 포함 된 필드를 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스입니다.

DEBUGPROP_INFO_VALUE_AUTOEXPAND 지정 값 필드는이 형식의 개체에 대 한 사용 가능한 경우 자동 확장 값을 포함 해야 합니다.

DEBUGPROP_INFO_VALUE_NOFUNCEVAL 사용 되지 않습니다.

또한 값 이나 멤버를 반환 하지 DEBUGPROP_INFO_VALUE_RAW 않습니다 (즉, 포맷 안 함 값).

합성 된 특수 한 값을 반환 하지 DEBUGPROP_INFO_VALUE_NO_TOSTRING 않습니다 (예를 들어 호출 하지 마십시오 `ToString()` 값을 생성 하는 개체에).

플래그가 설정 되지 않음 DEBUGPROP_INFO_NONE 지정 합니다.

DEBUGPROP_INFO_STANDARD 초기화/사용 된 `dwAttrib`, `bstrName`, `bstrType`, 및 `bstrValue` 필드입니다.

DEBUGPROP_INFO_All 모든 플래그 마스크를 나타냅니다.

## <a name="remarks"></a>설명
이러한 값에 전달 되는 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)를 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), 및 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 를 초기화할 수 있는 필드를 나타내는 방법을 [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다.

이러한 값에도 사용 됩니다 합니다 `dwFields` 의 멤버는 `DEBUG_PROPERTY_INFO` 구조 반환 되 면 유효 하 고 사용 되는 구조체의 필드는 구조체.

이러한 값을 비트 결합할 수 있습니다 `OR`합니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
- [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
