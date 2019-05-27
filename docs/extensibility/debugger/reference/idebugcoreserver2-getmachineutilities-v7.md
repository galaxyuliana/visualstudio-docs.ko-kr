---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0aff4ccea937536530d74dde13a5ba8a7b14bca7
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205680"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
이 메서드는 서버에 대 한 시스템 유틸리티를 가져옵니다.

> [!NOTE]
> 이 메서드는 사용 되지 않는: 사용 하지 마세요 ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 하는 경우). 기록을 위해 보존 됩니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetMachineUtilities_V7(
   IDebugMDMUtil2_V7** ppUtil
);
```

```csharp
int GetMachineUtilities_V7(
   out IDebugMDMUtil2_V7 ppUtil
);
```

## <a name="parameters"></a>매개 변수
`ppUtil`\
[out] 반환 된 `IDebugMDMUtil2_V7` 머신 유틸리티 정보를 나타내는 인터페이스입니다.

## <a name="return-value"></a>반환 값
 항상 반환 `E_NOTIMPL`, 메서드가 구현 되지 않았음을 나타내는입니다.

## <a name="remarks"></a>설명
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 합니다.

## <a name="see-also"></a>참고자료
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)