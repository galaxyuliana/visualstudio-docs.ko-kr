---
title: IDebugCustomAttribute::GetName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e744839b7f0461249f16afec7c2186adc26e245f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021340"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
사용자 지정 특성의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```csharp  
int GetName(  
   out string bstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bstrName`  
 [out] 사용자 지정 특성의 이름을 포함 하는 문자열을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 명명 된이 메서드에서 반환 되는 특성을 선언 하는 데 사용 하는 클래스의 이름에 해당 합니다. C#-선언에 사용 될 때 사용자 지정 특성 이름에서 삭제할 "특성" 접미사를 허용 하는 중 정확히 자체 사용자 지정 특성 클래스의 이름에 해당 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)