---
title: BP_COND_STYLE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 70ab3655d27e810b3c05d0e0e81d81bc15a26950
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685861"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
보류 중인 중단점 조건 스타일을 지정 하 고 바인딩된 중단점.

## <a name="syntax"></a>구문

```cpp
enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
typedef DWORD BP_COND_STYLE;
```

```csharp
public enum enum_BP_COND_STYLE {
    BP_COND_NONE         = 0x0000,
    BP_COND_WHEN_TRUE    = 0x0001,
    BP_COND_WHEN_CHANGED = 0x0002
};
```

## <a name="members"></a>멤버
BP_COND_NONE는 중단점의 위치에 도달 하면 중단점을 발생 시킵니다. 중단점 조건 지정 없습니다.

BP_COND_WHEN_TRUE로 조건식 중단점을 사용 하 여 연결 하는 경우에 중단점이 발생 `true`합니다.

중단점 조건 식의 값 중단점과 연결 된 경우에 해당 이전 평가에서 변경 된 BP_COND_WHEN_CHANGED 발생 합니다.

## <a name="remarks"></a>설명
에 사용 되는 합니다 `styleCondition` 의 멤버는 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 구조입니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
