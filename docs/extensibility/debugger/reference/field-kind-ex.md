---
title: FIELD_KIND_EX | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- FIELD_KIND_EX enumeration
ms.assetid: 922c3208-1e94-485f-b70a-3bc96affeff8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 97a2d4e76ebe1ed206ebbc2eea09b15865b86a2b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56700016"
---
# <a name="fieldkindex"></a>FIELD_KIND_EX
필드의 추가 종류를 열거 하는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체에 포함 될 수 있습니다. 이 열거형을 확장 합니다 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) 열거형입니다.

## <a name="syntax"></a>구문

```cpp
enum enum_FIELD_KIND_EX
{
    FIELD_KIND_EX_NONE = 0,
    FIELD_TYPE_EX_METHODVAR = 0x1,
    FIELD_TYPE_EX_CLASSVAR = 0x2
};
typedef DWORD FIELD_KIND_EX;
```

```csharp
public enum enum_FIELD_KIND_EX
{
    FIELD_KIND_EX_NONE = 0,
    FIELD_TYPE_EX_METHODVAR = 0x1,
    FIELD_TYPE_EX_CLASSVAR = 0x2
};
```

## <a name="members"></a>멤버
FIELD_KIND_EX_NONE 필드에는 확장된 유형이 없습니다.

FIELD_TYPE_EX_METHODVAR 필드 메서드 변수를 포함합니다.

FIELD_TYPE_EX_CLASSVAR 필드 클래스 변수를 포함합니다.

## <a name="requirements"></a>요구 사항
헤더: Sh.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)
