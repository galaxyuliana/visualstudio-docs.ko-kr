---
title: IDebugDocument2::GetDocumentClassID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2::GetDocumentClassID
helpviewer_keywords:
- IDebugDocument2::GetDocumentClassID
ms.assetid: 111c2b85-ebfa-487f-b896-2ec4a3eac4d1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e969d7c6f17aeaa8642b9988e741318ec1591d6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691256"
---
# <a name="idebugdocument2getdocumentclassid"></a>IDebugDocument2::GetDocumentClassID
문서 클래스 식별자를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetDocumentClassID( 
   CLSID* pclsid
);
```

```csharp
int GetDocumentClassID( 
   out Guid pclsid
);
```

#### <a name="parameters"></a>매개 변수
 `pclsid`

 [out] 문서 클래스 id는 GUID를 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 각각 문서를 나타내는 개별 클래스를 인스턴스화할 클래스 GUID를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)