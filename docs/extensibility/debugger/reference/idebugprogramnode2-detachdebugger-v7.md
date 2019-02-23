---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0b7d97e277a3f7f327bf8830e49507d28e82568f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56713700"
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> 사용 되지 않습니다. 사용 하지 마세요.

## <a name="syntax"></a>구문

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>반환 값

구현을 항상 반환 `E_NOTIMPL`합니다.

## <a name="remarks"></a>설명

> [!WARNING]
> Visual Studio 2005를 기준으로이 메서드는 더 이상 및 항상 반환 `E_NOTIMPL`합니다.

이 메서드는 디버거가 예기치 않게 종료 되는 경우 호출 됩니다. 이 메서드를 호출 하는 경우는 DE에서 분리 된 사용자 처럼 프로그램을 재개 해야 합니다. 디버그 이벤트가 더 이상 전송 되어야 합니다. 프로그램은 디버거의 다른 인스턴스에서 연결 가능한 상태에 있어야 합니다.

## <a name="see-also"></a>참고 항목

- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)