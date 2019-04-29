---
title: IDebugEngine2::CauseBreak | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa0d559887019a697b820a5a6c91f80b78c6b713
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920958"
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
이 디버그 엔진 (DE) 다음에 실행을 중지 하 여 디버깅 중인 모든 프로그램 요청 실행 하려고 해당 스레드 중 하나입니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CauseBreak( 
   void 
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드는 비동기:는 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 프로그램은 다음이 메서드가 호출 된 후 실행 하려고 할 때 이벤트를 보냅니다.

## <a name="see-also"></a>참고 항목
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)