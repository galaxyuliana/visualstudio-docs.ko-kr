---
title: IDebugDefaultPort2::GetServer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::GetServer
helpviewer_keywords:
- IDebugDefaultPort2::GetServer
ms.assetid: cacb4b74-0f39-471c-af38-54b73f5b2868
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2cbfc81495c1f2319117a236246f1e7c47f3e582
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875986"
---
# <a name="idebugdefaultport2getserver"></a>IDebugDefaultPort2::GetServer
이 메서드는이 포트에 있는 서버에 대 한 인터페이스를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetServer(
   IDebugCoreServer3** ppServer
);
```

```csharp
int GetServer(
   out IDebugCoreServer3 ppServer
);
```

#### <a name="parameters"></a>매개 변수
 `ppServer`

 [out] 구현 하는 개체를 반환 합니다 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md) 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 합니다 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md) Visual Studio에서 구현 되 고 포트에 있는 서버를 나타냅니다.

## <a name="see-also"></a>참고 항목
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)