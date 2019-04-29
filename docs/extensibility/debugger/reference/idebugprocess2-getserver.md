---
title: IDebugProcess2::GetServer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetServer
helpviewer_keywords:
- IDebugProcess2::GetServer
ms.assetid: 8f73c530-cceb-4f1f-8c63-1cc0ccd4a310
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33f9b513bcf336cac68af7d915880af0652b0954
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917767"
---
# <a name="idebugprocess2getserver"></a>IDebugProcess2::GetServer
이 프로세스에서 실행 되는 서버를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetServer( 
   IDebugCoreServer2** ppServer
);
```

```csharp
int GetServer( 
   out IDebugCoreServer2 ppServer
);
```

#### <a name="parameters"></a>매개 변수
 `ppServer`

 [out] 반환 된 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 이 프로세스를 실행 중인 서버를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 단일 컴퓨터에서 둘 이상의 서버를 실행할 수 있습니다.

## <a name="see-also"></a>참고 항목
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)