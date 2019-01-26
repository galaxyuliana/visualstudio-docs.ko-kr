---
title: IDebugEngine2::SetMetric | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2:::SetMetric
helpviewer_keywords:
- IDebugEngine2:::SetMetric
ms.assetid: dcda4972-c32e-4693-a0e1-25d5c58b9782
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f50732b6e271ac3bf51eb2cde4549cd7396fb4b8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998198"
---
# <a name="idebugengine2setmetric"></a>IDebugEngine2::SetMetric
이 메서드를 기준으로 알려진 레지스트리 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetMetric(  
   LPCOLESTR pszMetric,  
   VARIANT   varValue  
);  
```  
  
```csharp  
int SetMetric(  
   string pszMetric,  
   object varValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszMetric`  
 [in] 메트릭 이름입니다.  
  
 `varValue`  
 [in] 메트릭 값을 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 메트릭은 디버그 엔진의 동작을 변경 하거나 지원 되는 기능을 보급 하는 데 사용 하는 레지스트리 값입니다. 이 메서드는 적절 한 형식에 대 한 호출을 전달할 수 있습니다 합니다 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 함수를 `SetMetric`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)