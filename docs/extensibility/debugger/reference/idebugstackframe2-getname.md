---
title: IDebugStackFrame2::GetName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetName
helpviewer_keywords:
- IDebugStackFrame2::GetName
ms.assetid: 069d4f96-363f-404e-9c89-5318c4c9821b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ee4c292bdd80a8209d9136bac0cbc6775a2c33ac
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458520"
---
# <a name="idebugstackframe2getname"></a>IDebugStackFrame2::GetName
스택 프레임의 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetName ( 
   BSTR* pbstrName
);
```

```csharp
int GetName ( 
   out string pbstrName
);
```

## <a name="parameters"></a>매개 변수
 `pbstrName`\

 [out] 스택 프레임의 이름을 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 스택 프레임의 이름은 일반적으로 실행 중인 메서드의 이름입니다.

## <a name="see-also"></a>참고자료
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)