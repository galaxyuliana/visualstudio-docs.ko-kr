---
title: CONNECTION_PROTOCOL | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONNECTION_PROTOCOL
helpviewer_keywords:
- CONNECTION_PROTOCOL enumeration
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2a7d8d056fb816a428d78a8e13455cf6ccdd8a90
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56705835"
---
# <a name="connectionprotocol"></a>CONNECTION_PROTOCOL
디버그 패키지 (DE) 및 디버그 서버 간의 통신에 사용 되는 프로토콜을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
typedef enum tagCONNECTION_PROTOCOL {
    CONNECTION_NONE    = 0,
    CONNECTION_UNKNOWN = 1,
    CONNECTION_LOCAL   = 2,
    CONNECTION_PIPE    = 3,
    CONNECTION_TCPIP   = 4,
    CONNECTION_HTTP    = 5,
    CONNECTION_OTHER   = 6
} CONNECTION_PROTOCOL;
```

```csharp
public enum CONNECTION_PROTOCOL {
    CONNECTION_NONE    = 0,
    CONNECTION_UNKNOWN = 1,
    CONNECTION_LOCAL   = 2,
    CONNECTION_PIPE    = 3,
    CONNECTION_TCPIP   = 4,
    CONNECTION_HTTP    = 5,
    CONNECTION_OTHER   = 6
};
```

#### <a name="parameters"></a>매개 변수
서버에 연결 CONNECTION_NONE 없음 했습니다.

CONNECTION_UNKNOWN는 연결 된 내용이 있지만 알 수 없는 형식입니다.

로컬 서버 CONNECTION_LOCAL 연결입니다.

명명 된 파이프를 통해 CONNECTION_PIPE 연결이 있습니다.

CONNECTION_TCPIP 연결에서 TCP/IP를 사용 합니다.

CONNECTION_HTTP 연결은 (웹 서버)를 통해 HTTP를 사용합니다.

다른 유형의 연결을 설정한 CONNECTION_OTHER (이 값은 현재 사용 되지).

## <a name="remarks"></a>설명
이러한 값이 반환 된 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)
