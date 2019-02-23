---
title: IDebugDocumentContext2::GetDocument | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetDocument
helpviewer_keywords:
- IDebugDocumentContext2::GetDocument
ms.assetid: c6d46c5d-ade8-4dc8-9862-8fc7876658c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1617bf6b2d2e50129998e61b2d05de593054d166
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678010"
---
# <a name="idebugdocumentcontext2getdocument"></a>IDebugDocumentContext2::GetDocument
이 문서 컨텍스트를 포함 하는 문서를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetDocument( 
   IDebugDocument2** ppDocument
);
```

```csharp
int GetDocument( 
   out IDebugDocument2 ppDocument
);
```

#### <a name="parameters"></a>매개 변수
 `ppDocument`

 [out] 반환 된 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 이 문서 컨텍스트를 포함 하는 문서를 나타내는 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 이 메서드는 IDE에 직접 문서를 제공 하는 해당 디버그 엔진입니다. 그렇지 않으면이 메서드에서 반환 해야 `E_NOTIMPL`합니다.

## <a name="see-also"></a>참고 항목
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)