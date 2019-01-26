---
title: IDebugObject2::IsEncOutdated | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c5facc3b8efed46817e99624e6b019d1498ec622
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55016137"
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
이 메서드는 부모 컨테이너 또는이 개체의 편집 하며 계속 하기 상태 최신 인지 확인 합니다. 이 메서드와 항상 반환을 사용자 지정 식 계산기 구현 하지 않는 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```csharp  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfEncOutdated`  
 [out] 0이 아닌 값 (`TRUE`) 편집 하며 계속 하기 상태를 오래 된 경우에 0 (`FALSE`) 없는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  사용자 지정 식 계산기는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)