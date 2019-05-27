---
title: IDebugReference2::SetValueAsString | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsString
helpviewer_keywords:
- IDebugReference2::SetValueAsString
ms.assetid: 9a508ced-fd54-44f5-bb42-ec15c80384d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ca994aaf03103e6d668d78a7d3a683ddbc988eb7
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210091"
---
# <a name="idebugreference2setvalueasstring"></a>IDebugReference2::SetValueAsString
문자열에서 참조의 값을 설정 합니다. 나중에 사용하기 위해 예약되어 있습니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   DWORD     dwRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   dwRadix,
   uint   dwTimeout
);
```

## <a name="parameters"></a>매개 변수
`pszValue`\
[in] 문자열로 나타낸 값입니다.

`dwRadix`\
[in] 모든 숫자 정보를 서식 지정 하는 데 사용할 기 수입니다.

`dwTimeout`\
[in] 이 메서드에서 반환 되기 전에 대기할 밀리초에서는 최대 시간입니다. 사용 하 여 `INFINITE` 무기한 대기 합니다.

## <a name="return-value"></a>반환 값
 항상 `E_NOTIMPL`를 반환합니다.

## <a name="see-also"></a>참고자료
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)