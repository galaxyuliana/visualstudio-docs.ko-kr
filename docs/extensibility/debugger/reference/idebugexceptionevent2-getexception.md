---
title: IDebugExceptionEvent2::GetException | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExceptionEvent2::GetException
helpviewer_keywords:
- IDebugExceptionEvent2::GetException
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 79385348aa9290f26a34b99dbd2d6f68cb92dc8a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680284"
---
# <a name="idebugexceptionevent2getexception"></a>IDebugExceptionEvent2::GetException
이 이벤트를 발생 시킨 예외에 대 한 자세한 설명을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetException( 
   EXCEPTION_INFO* pExceptionInfo
);
```

```csharp
int GetException( 
   EXCEPTION_INFO[] pExceptionInfo
);
```

#### <a name="parameters"></a>매개 변수
 `pExceptionInfo`

 [out에서] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 구조 설명은 예외를 사용 하 여 입력 됩니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명

 [C + + 전용] 호출자가에서 모든 문자열을 해제 하는 일을 담당 합니다 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 해제와 구조체를 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 구조의 개체.

## <a name="see-also"></a>참고 항목
- [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)