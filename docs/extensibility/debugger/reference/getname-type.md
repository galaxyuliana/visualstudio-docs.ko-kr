---
title: GETNAME_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ba394d725afd45664ad6cf4f69c9e048b7e1a74d
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413113"
---
# <a name="getnametype"></a>GETNAME_TYPE
검색할 파일 이름 형식을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
typedef DWORD GETNAME_TYPE;
```

```csharp
public enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
```

## <a name="members"></a>멤버
GN_NAME  
문서 또는 상황에 맞는 이름을 지정합니다.

GN_FILENAME  
문서 또는 상황에 맞는의 전체 경로 지정합니다.

GN_BASENAME  
문서 또는 상황에 맞는의 전체 경로 대신 기본 파일 이름을 지정합니다.

GN_MONIKERNAME  
모니커의 형식 문서 또는 상황에 맞는의 고유한 이름을 지정합니다.

GN_URL  
문서 또는 컨텍스트 URL 이름을 지정합니다.

GN_TITLE  
있을 경우 문서의 제목을 지정 합니다.

GN_STARTPAGEURL  
프로세스에 대 한 시작 페이지 URL을 가져옵니다.

## <a name="remarks"></a>설명
이러한 값을 매개 변수로 전달 되는 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)를 [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md), 및 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) 반환할 이름의 종류를 지정 하는 방법입니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)  
[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)  
[GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
