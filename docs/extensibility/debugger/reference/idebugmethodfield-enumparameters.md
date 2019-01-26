---
title: IDebugMethodField::EnumParameters | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6eb2272aff9f02e4de85c5420bd687b059c0e839
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035446"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
메서드의 매개 변수에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppParams`  
 [out] 반환 합니다는 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 메서드에 매개 변수 목록을 나타내는 개체;이 고, 그렇지 매개 변수가 없는 경우 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 매개 변수가 없는 경우 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 각 요소는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 다른 형식의 매개 변수를 나타내는 개체입니다. 호출 된 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 정확히 어떤 종류의 매개 변수 개체가 나타내는 확인 하려면 각 개체의 메서드.  
  
 매개 변수 이름 및 해당 형식 둘 다 포함 됩니다. 클래스 메서드에 첫 번째 매개 변수는 일반적으로 "this"이 포인터입니다.  
  
 매개 변수의 형식에 필요한 경우 호출 된 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)