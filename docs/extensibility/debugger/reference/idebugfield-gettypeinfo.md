---
title: IDebugField::GetTypeInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetTypeInfo
helpviewer_keywords:
- IDebugField::GetTypeInfo method
ms.assetid: bb5acfa3-04c3-4088-be84-9ff8926cd16f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 781c9a0e4365a454d45af957207099d6d5ae7d92
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212650"
---
# <a name="idebugfieldgettypeinfo"></a>IDebugField::GetTypeInfo
이 메서드는 기호 또는 형식에 대 한 형식에 관계 없이 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetTypeInfo( 
   TYPE_INFO* pTypeInfo
);
```

```csharp
int GetTypeInfo(
   TYPE_INFO[] pTypeInfo
);
```

## <a name="parameters"></a>매개 변수
`pTypeInfo`\
[out] 제공 된 정보를 입력 하는 반환 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) 구조입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 예를 들어, AppDomain, 모듈 및 기호를 포함 하는 클래스 형식에 관계 없이 정보가 포함 됩니다.

## <a name="see-also"></a>참고자료
- [GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)