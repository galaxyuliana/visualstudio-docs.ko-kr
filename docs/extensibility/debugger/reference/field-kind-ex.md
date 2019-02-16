---
title: FIELD_KIND_EX | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- FIELD_KIND_EX enumeration
ms.assetid: 922c3208-1e94-485f-b70a-3bc96affeff8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28a880af0a5d691a57e32b22f9f7823cca45827d
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317785"
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
FIELD_KIND_EX_NONE  
필드에는 확장된 유형이 없습니다.

FIELD_TYPE_EX_METHODVAR  
필드는 메서드 변수를 포함합니다.

FIELD_TYPE_EX_CLASSVAR  
필드는 클래스 변수를 포함합니다.

## <a name="requirements"></a>요구 사항
헤더: Sh.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)
