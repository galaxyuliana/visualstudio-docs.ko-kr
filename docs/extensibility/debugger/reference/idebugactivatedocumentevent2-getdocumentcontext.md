---
title: IDebugActivateDocumentEvent2::GetDocumentContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugActivateDocumentEvent2::GetDocumentContext
helpviewer_keywords:
- GetDocumentContext method
- IDebugActivateDocumentEvent2::GetDocumentContext method
ms.assetid: e7472069-7337-4ef4-8f8a-8c027a2e22f4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4706a10a73e0ed62a03baaf4027906ce37006dcc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920606"
---
# <a name="idebugactivatedocumentevent2getdocumentcontext"></a>IDebugActivateDocumentEvent2::GetDocumentContext
디버그 패키지가 현재 수에 있는 문서의 위치를 설명 하는 문서 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocumentContext (   
   IDebugDocumentContext2** ppDocContext  
);  
```  
  
```csharp  
int GetDocumentContext (   
   out IDebugDocumentContext2 ppDocContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppDocContext`  
 [out] 반환 된 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 원본 파일 문서의 위치를 나타내는 개체입니다.  
  
## <a name="remarks"></a>설명  
 예를 들어 캐럿을 표시 하려면이 위치를 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)