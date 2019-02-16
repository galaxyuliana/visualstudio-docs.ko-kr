---
title: BP_LOCATION_CODE_FILE_LINE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_FILE_LINE
helpviewer_keywords:
- BP_LOCATION_CODE_FILE_LINE structure
ms.assetid: 3ff32032-d412-44d3-91bf-870cc354a09e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ab7a0b226b7a8fac779e5c5109700a37e60d9d0
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315705"
---
# <a name="bplocationcodefileline"></a>BP_LOCATION_CODE_FILE_LINE
코드 소스 파일의 특정 줄 중단점의 위치에 대 한 데이터를 포함합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct _BP_LOCATION_CODE_FILE_LINE {
    BSTR                     bstrContext;
    IDebugDocumentPosition2* pDocPos;
} BP_LOCATION_CODE_FILE_LINE;
```

## <a name="members"></a>멤버
`bstrContext`  
중단점의 컨텍스트에서, 일반적으로 호출 스택에 표시 된 메서드 또는 함수의 이름입니다.

`pDocPos`  
합니다 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) 중단점의 문서 위치를 나타내는 개체입니다.

## <a name="remarks"></a>설명
이 구조체의 멤버인 합니다 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체의 일부로 구조입니다.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
