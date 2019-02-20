---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- GETHOSTNAME_TYPE
helpviewer_keywords:
- GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f158cdaba17c030ce830c8adf26b6985c9b86dad
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413438"
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
호스트 이름의 형식을 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_GETHOSTNAME_TYPE {
    GHN_FRIENDLY_NAME = 0,
    GHN_FILE_NAME     = 1
};
typedef DWORD GETHOSTNAME_TYPE;
```

```csharp
public enum enum_GETHOSTNAME_TYPE {
    GHN_FRIENDLY_NAME = 0,
    GHN_FILE_NAME     = 1
};
```

## <a name="members"></a>멤버
GHN_FRIENDLY_NAME  
호스트의 이름을 지정합니다.

GHN_FILE_NAME  
호스트의 파일 이름을 지정합니다.

## <a name="remarks"></a>설명
이러한 값을 인수로 전달 되는 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 다양 한 형식에서 호스트 이름을 검색 하는 방법입니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)
