---
title: IDebugDocumentContext2::Seek | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f001eb73e3c24ac1c9f15a4bd2c37c8d2cbe660e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709527"
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
문이나 줄의 지정된 된 수 만큼 문서 컨텍스트를 이동합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Seek( 
   int                      nCount,
   IDebugDocumentContext2** ppDocContext
);
```

```cpp
int Seek( 
   int                        nCount,
   out IDebugDocumentContext2 ppDocContext
);
```

#### <a name="parameters"></a>매개 변수
 `nCount`

 [in] 문 또는 문서 컨텍스트에 따라 미리 이동할 줄 수입니다.

 `ppDocContext`

 [out] 반환 된 새 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 새 위치를 사용 하 여 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)