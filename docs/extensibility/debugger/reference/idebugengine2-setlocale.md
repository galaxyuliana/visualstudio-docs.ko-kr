---
title: IDebugEngine2::SetLocale | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::SetLocale
helpviewer_keywords:
- IDebugEngine2::SetLocale
ms.assetid: cd0d2cf1-2aac-43da-a830-4bb3d696c219
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e0434904b71ff1858cc784396fbafa40096d7669
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66207505"
---
# <a name="idebugengine2setlocale"></a>IDebugEngine2::SetLocale
디버그 엔진 (DE)의 로캘을 설정합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetLocale( 
   WORD wLangID
);
```

```csharp
int SetLocale( 
   ushort wLangID
);
```

## <a name="parameters"></a>매개 변수
`wLangID`\
[in] 언어 로캘을 지정합니다. 예를 들어 1033 사용 하 여 영어 지정 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드는 SDM ()는 DE 반환한 문자열이 지역화 제대로 됩니다 있도록 IDE의 로캘 설정을 전파 하는 데 세션 디버그 관리자에 의해 호출 됩니다.

## <a name="see-also"></a>참고자료
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)