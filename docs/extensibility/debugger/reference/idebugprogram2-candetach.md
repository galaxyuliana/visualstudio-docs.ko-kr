---
title: IDebugProgram2::CanDetach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::CanDetach
helpviewer_keywords:
- IDebugProgram2::CanDetach
ms.assetid: dcd9ab6c-49e5-447e-aa7c-89f571f4a052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fc95cee8a463337564ddfec5322ab074e3485bc1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693602"
---
# <a name="idebugprogram2candetach"></a>IDebugProgram2::CanDetach
디버그 엔진 (DE) 프로그램에서 분리 하는 경우를 결정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CanDetach(
   void
);
```

```csharp
int CanDetach();
```

## <a name="return-value"></a>반환 값
 경우를 분리 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `S_FALSE` 경우는 DE 프로그램에서 분리할 수 없습니다.

## <a name="see-also"></a>참고 항목
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)