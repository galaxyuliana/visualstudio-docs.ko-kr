---
title: MESSAGETYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 16d2b9ae9c446d4c8082a8c35c9e4d1810233b95
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687512"
---
# <a name="messagetype"></a>MESSAGETYPE
메시지 유형 및 이유를 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_MESSAGETYPE { 
   MT_OUTPUTSTRING      = 0x0000001,
   MT_MESSAGEBOX        = 0x00000002,
   MT_TYPE_MASK         = 0x000000FF,
   MT_REASON_EXCEPTION  = 0x00000100,
   MT_REASON_TRACEPOINT = 0x00000200,
   MT_REASON_MASK       = 0x0000FF00
};
typedef DWORD MESSAGETYPE;
```

```csharp
public enum enum_MESSAGETYPE { 
   MT_OUTPUTSTRING      = 0x0000001,
   MT_MESSAGEBOX        = 0x00000002,
   MT_TYPE_MASK         = 0x000000FF,
   MT_REASON_EXCEPTION  = 0x00000100,
   MT_REASON_TRACEPOINT = 0x00000200,
   MT_REASON_MASK       = 0x0000FF00
};
```

## <a name="members"></a>멤버
 출력 창에 메시지를 보낼 수 해야 MT_OUTPUTSTRING 나타냅니다. 이 상호 배타적인에서 `MT_MESSAGEBOX`합니다.

 MT_MESSAGEBOX 메시지 상자에 메시지를 표시할지 나타냅니다. 이 상호 배타적인에서 `MT_OUTPUTSTRING`합니다.

 메시지에 대 한 대상 격리 MT_TYPE_MASK는 마스크 값입니다.

 MT_REASON_EXCEPTION 예외 결과로 메시지 상자가 표시 되는 나타냅니다. 이 상호 배타적인에서 `MT_REASON_TRACEPOINT`합니다.

 MT_REASON_TRACEPOINT 추적점에 도달 하는 결과로 메시지 상자가 표시 되는 나타냅니다. 이 상호 배타적으로 `MT_REASON_EXCEPTION`입니다.

 표시 되는 메시지에 대 한 이유를 격리 하는 마스크 값 MT_REASON_MASK입니다.

## <a name="remarks"></a>설명
 이러한 값이 반환 된 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) 하 고 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) 메서드.

 비트를 사용 하 여 출력 대상 값 중 하나를 사용 하 여 결합할 수 이유 값 중 하나로 `OR`합니다.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)
- [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)