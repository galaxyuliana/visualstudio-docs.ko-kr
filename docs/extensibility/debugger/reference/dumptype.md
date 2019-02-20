---
title: DUMPTYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DUMPTYPE
helpviewer_keywords:
- DUMPTYPE enumeration
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c81d9c9f3f5dc6b0a849e405133b7ecef1e4e59b
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56412970"
---
# <a name="dumptype"></a>DUMPTYPE
덤프 하는 데 얼마나 많은 프로그램의 상태 (예: 실행 중인 스레드, 스택 프레임 및 현재 명령 주소)를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_DUMPTYPE {
    DUMP_MINIDUMP = 0,
    DUMP_FULLDUMP = 1
};
typedef DWORD DUMPTYPE;
```

```csharp
public enum enum_DUMPTYPE {
    DUMP_MINIDUMP = 0,
    DUMP_FULLDUMP = 1
};
```

## <a name="members"></a>멤버
DUMP_MINIDUMP  
작은, compact 덤프를 지정합니다.

DUMP_FULLDUMP  
큰, 전체 덤프를 지정합니다.

## <a name="remarks"></a>설명
인수로 전달 된 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)
