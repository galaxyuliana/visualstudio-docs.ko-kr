---
title: IDebugQueryEngine2::GetEngineInterface | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbb4f5018972777e51fbaad8d06f833309f6390f
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212933"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
사용자 지정 디버그 엔진 (DE) 인터페이스를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetEngineInterface( 
   IUnknown** ppUnk
);
```

```csharp
int GetEngineInterface( 
   out object ppUnk
);
```

## <a name="parameters"></a>매개 변수
`ppUnk`\
[out] 반환 된 `IUnknown` 디버그 엔진 (DE), 및는 DE로 연결 된 다른 모든 유효한 인터페이스를 쿼리할 수 있는 개체를 나타냅니다 (예를 들어 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 또는 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드에서 검색 하는 인터페이스를 통해 호출 세션 디버그 관리자의 처리를 우회 하 고 SDM 잘못 된 상태로 시작 또는 디버그 하는 동안 오류가 발생 될 수 있습니다 결과 인터페이스 주의 해 서 사용 해야 합니다.

## <a name="see-also"></a>참고자료
- [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)