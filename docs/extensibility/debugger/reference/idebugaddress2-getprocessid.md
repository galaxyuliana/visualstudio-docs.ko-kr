---
title: IDebugAddress2::GetProcessID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d2fce11c4ddd5a2ca882749ff4ae4a9b3ee0434
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723320"
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
이 나타내는 개체를 소유 하는 프로세스의 ID를 가져옵니다 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetProcessID (
   DWORD* pProcID
);
```

```csharp
int GetProcessID (
   out uint pProcID
);
```

#### <a name="parameters"></a>매개 변수
 `pProcID`

 [out] 프로세스 id입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="see-also"></a>참고 항목
- [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)