---
title: IDebugProgram2::EnumCodeContexts | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::EnumCodeContexts
helpviewer_keywords:
- IDebugProgram2::EnumCodeContexts
ms.assetid: 478e06a2-07bb-4841-8887-deab0f42ebd0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 77d92a65b77cbec94a6c74852393627af6763bad
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685393"
---
# <a name="idebugprogram2enumcodecontexts"></a>IDebugProgram2::EnumCodeContexts
소스 파일에서 지정된 된 위치에 대 한 코드 컨텍스트의 목록을 검색합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumCodeContexts( 
   IDebugDocumentPosition2*  pDocPos,
   IEnumDebugCodeContexts2** ppEnum
);
```

```csharp
int EnumCodeContexts( 
   IDebugDocumentPosition2     pDocPos,
   out IEnumDebugCodeContexts2 ppEnum
);
```

#### <a name="parameters"></a>매개 변수
 `pDocPos`

 [in] [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) IDE에 알려진 소스 파일에서 추상 위치를 나타내는 개체입니다.

 `ppEnum`

 [out] 반환 된 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md) 코드 컨텍스트의 목록을 포함 하는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 방법을 사용 하면 세션 디버그 관리자 (SDM) 또는 IDE에서 코드 위치에 원본 파일 위치를 매핑합니다. 둘 이상의 코드 컨텍스트는 소스 코드 (예: c + + 템플릿)의 여러 요소를 생성 하는 경우 반환 됩니다.

## <a name="see-also"></a>참고 항목
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
- [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)