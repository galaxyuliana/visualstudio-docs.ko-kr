---
title: IDebugProgramPublisher2::PublishProgram | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 04c63a2a18f04301e16dd0e8137ab8ba4b824c57
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457868"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
이 메서드는 디버그 엔진 (DEs)에 사용할 수 있는 프로그램 및 세션 디버그 관리자를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT PublishProgram(
   CONST_GUID_ARRAY Engines,
   LPCOLESTR        szFriendlyName,
   IUnknown*        pDebuggeeInterface
);
```

```csharp
int PublishProgram(
   CONST_GUID_ARRAY Engines,
   string           szFriendlyName,
   object           pDebuggeeInterface
);
```

## <a name="parameters"></a>매개 변수
 `Engines`\

 [in] Des 시작 하거나이 프로그램을 연결할 수 있는 Guid의 배열입니다.

 `szFriendlyName`\

 [in] \(메뉴 또는 대화 상자에는 사용자에 게 표시) 프로그램에 대 한 이름입니다.

 `pDebuggeeInterface`\

 [in] `IUnknown` 프로그램에 대 한 인터페이스 (이 값은 고유 하 게 프로그램을 식별 하는 쿠키로 사용;이 동일한 값이 "프로그램을 게시 취소"를 사용)

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 프로그램을 디버깅을 위해 더 이상 사용할 수 있도록 하려면 호출 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)합니다.

## <a name="see-also"></a>참고자료
- [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)
- [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)