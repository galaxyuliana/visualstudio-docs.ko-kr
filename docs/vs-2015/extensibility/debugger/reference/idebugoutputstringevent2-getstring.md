---
title: IDebugOutputStringEvent2::GetString | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugOutputStringEvent2::GetString
helpviewer_keywords:
- IDebugOutputStringEvent2::GetString
ms.assetid: f059f8e0-ad44-49ac-ba90-73576ada5e06
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ab26e1b7094d387562fface2c2d0945b0dfe89b9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981497"
---
# <a name="idebugoutputstringevent2getstring"></a>IDebugOutputStringEvent2::GetString
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

표시할 수 있는 메시지를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetString(   
   BSTR* pbstrString  
);  
```  
  
```csharp  
int GetString(   
   out string pbstrString  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrString`  
 [out] 표시 가능한 메시지가 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugOutputStringEvent2](../../../extensibility/debugger/reference/idebugoutputstringevent2.md)
