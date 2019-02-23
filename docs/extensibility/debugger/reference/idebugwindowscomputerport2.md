---
title: IDebugWindowsComputerPort2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugWindowsComputerPort2 interface
ms.assetid: 25f327b8-0303-4268-88d1-74df630436aa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9126d7507f47852b7fc9bcd3777b112932892bb4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702150"
---
# <a name="idebugwindowscomputerport2"></a>IDebugWindowsComputerPort2
대상 컴퓨터에 대 한 정보를 쿼리할 수 있습니다.

## <a name="syntax"></a>구문

```
IDebugWindowsComputerPort2 : IUnknown
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 이 인터페이스는 세션 디버그 관리자의 포트 개체에 의해 구현 됩니다.

## <a name="methods"></a>메서드
 다음 표에서의 메서드를 보여 줍니다. `IDebugWindowsComputerPort2`합니다.

|메서드|설명|
|------------|-----------------|
|[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)|컴퓨터에 대 한 정보를 검색 디버거의 실행 합니다.|

## <a name="requirements"></a>요구 사항
 헤더: Msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll