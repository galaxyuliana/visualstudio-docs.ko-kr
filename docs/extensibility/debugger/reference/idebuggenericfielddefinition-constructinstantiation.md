---
title: IDebugGenericFieldDefinition::ConstructInstantiation | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 83284124f4cdf2fce49812998b6444fa43dc958e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954945"
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
지정 된 형식 인수 배열을 필드 인스턴스를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```csharp  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cArgs`  
 [in] 인수 개수는 `ppArgs` 배열입니다.  
  
 `ppArgs`  
 [in] 형식 인수를 포함 하는 배열입니다. 형식 인수에는 닫힌된 형식 (제네릭이 아닌 또는 완전히 인스턴스화된 제네릭) 이어야 합니다.  
  
 `ppConstructedField`  
 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 새 필드를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 제약 조건은 확인 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)