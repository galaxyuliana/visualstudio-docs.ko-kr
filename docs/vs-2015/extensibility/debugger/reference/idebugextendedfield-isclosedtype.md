---
title: IDebugExtendedField::IsClosedType | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a1cf28e8391a1dd37949c042bd7d58d9c8b7da06
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58971035"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

필드 닫힌된 형식을 나타내는지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>반환 값  
 필드에 닫힌된 형식이 면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
