---
title: IDebugSymbolProvider::GetClassTypeByName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetClassTypeByName
helpviewer_keywords:
- IDebugSymbolProvider::GetClassTypeByName method
ms.assetid: 2c748909-51dc-49b7-b193-19f96fca1138
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 20af990c6a32312cbab8496ca0bd2bae31b657ee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984381"
---
# <a name="idebugsymbolprovidergetclasstypebyname"></a>IDebugSymbolProvider::GetClassTypeByName
이 메서드는 정규화 된 클래스 이름을 나타내는 클래스 필드 형식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetClassTypeByName(   
   LPCOLESTR          pszClassName,  
   NAME_MATCH         nameMatch,  
   IDebugClassField** ppField  
);  
```  
  
```csharp  
int GetClassTypeByName(  
   string               pszClassName,   
   NAME_MATCH           nameMatch,   
   out IDebugClassField ppField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszClassName`  
 [in] 클래스 이름입니다.  
  
 `nameMatch`  
 [in] 형식을 일치, 예를 들어, 대/소문자 구분을 선택합니다. 값을 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) 열거형입니다.  
  
 `ppField`  
 [out] 에 표시 된 대로 클래스 형식을 반환 합니다 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)