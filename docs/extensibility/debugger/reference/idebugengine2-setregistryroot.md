---
title: IDebugEngine2::SetRegistryRoot | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::SetRegistryRoot
helpviewer_keywords:
- IDebugEngine2::SetRegistryRoot
ms.assetid: d0d81202-8a4a-4bc3-b297-30a047c5ec60
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d469dff028b0139c225b89e256896e6815f5e4fc
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66207472"
---
# <a name="idebugengine2setregistryroot"></a>IDebugEngine2::SetRegistryRoot
디버그 엔진 (DE)에 대 한 레지스트리 루트를 설정합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetRegistryRoot( 
   LPCOLESTR pszRegistryRoot
);
```

```csharp
int SetRegistryRoot( 
   string pszRegistryRoot
);
```

## <a name="parameters"></a>매개 변수
`pszRegistryRoot`\
[in] 사용할 레지스트리 루트입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 방법을 사용 하면 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 는 DE 레지스트리 설정을; 얻기 위해 사용 해야 하는 대체 레지스트리 루트를 지정 하려면 예를 들어, "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp"입니다.

## <a name="see-also"></a>참고자료
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)