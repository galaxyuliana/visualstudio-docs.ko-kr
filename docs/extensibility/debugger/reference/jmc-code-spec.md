---
title: JMC_CODE_SPEC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab69cdaa450ffd083aca25de1cab038a4b891baa
ms.sourcegitcommit: 845442e2b515c3ca1e4e47b46cc1cef4df4f08d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56449597"
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
이 구조는 모듈에 대 한 JustMyCode 정보 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
typedef struct _JMC_CODE_SPEC {
    BOOL fIsUserCode;
    BSTR bstrModuleName;
} JMC_CODE_SPEC;
```

```csharp
public struct JMC_CODE_SPEC {
    public int    fIsUserCode;
    public string bstrModuleName;
};
```

## <a name="members"></a>멤버
fIsUserCode 0이 아닌 (`TRUE`)이 모듈은 사용자 코드를 고려해 야 하는 경우 0이 고, 그렇지 (`FALSE`) 모듈이 외부 코드로 처리할 수 고를 디버깅할 경우.

bstrModuleName 해당 모듈의 이름입니다.

## <a name="remarks"></a>설명
이 구조는 이러한 구조를 목록으로 전달 되는 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)  
[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)
