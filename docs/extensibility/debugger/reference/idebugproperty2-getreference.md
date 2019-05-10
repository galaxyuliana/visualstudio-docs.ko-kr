---
title: IDebugProperty2::GetReference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9248ad59a564207befb0b0a3ff1c229840ee336b
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457726"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
속성의 값에 대 한 참조를 반환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetReference(
   IDebugReference2** ppReference
);
```

```csharp
int GetReference(
   out IDebugReference2 ppReference
);
```

## <a name="parameters"></a>매개 변수
 `ppRererence`\

 [out] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 속성의 값에 대 한 참조를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 오류 코드를 일반적으로 반환 `E_NOTIMPL` 또는 `E_GETREFERENCE_NO_REFERENCE`합니다.

## <a name="see-also"></a>참고자료
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)