---
title: IDebugProcess3::DisableENC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 65f79b73eaa9b97630cc3ef3e84e1ba4198835c9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66202354"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
이 메서드가 명시적으로 편집 하며 계속 하기가 비활성화가이 프로세스에 대 한 포함 하는 모든 프로그램. 사용자 지정 포트 공급자는 항상 반환 `E_NOTIMPL`합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT DisableENC(
   EncUnavailableReason reason
);
```

```csharp
   EncUnavailableReason reason
);
```

## <a name="parameters"></a>매개 변수
`reason`\
[in] 값을 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) 열거형입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

> [!NOTE]
> 사용자 지정 포트 공급자는 항상 반환 `E_NOTIMPL`합니다.

## <a name="remarks"></a>설명
 한 번 편집 하 고 프로세스를 계속 사용할 수 없습니다만 프로세스를 다시 시작 하 여 다시 활성화할 수 있습니다.

## <a name="see-also"></a>참고자료
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)