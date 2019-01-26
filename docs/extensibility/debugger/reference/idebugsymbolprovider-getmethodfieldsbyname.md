---
title: IDebugSymbolProvider::GetMethodFieldsByName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetMethodFieldsByName
helpviewer_keywords:
- IDebugSymbolProvider::GetMethodFieldsByName method
ms.assetid: 1f781320-81ef-4037-b068-f1864b271258
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5103752cd906a2d82063d63cde53776d5f4b9d36
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998887"
---
# <a name="idebugsymbolprovidergetmethodfieldsbyname"></a>IDebugSymbolProvider::GetMethodFieldsByName
이 메서드는 정규화 된 메서드 이름을 나타내는 필드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodFieldsByName(   
   LPCOLESTR          pszFullName,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int GetMethodFieldsByName(  
   string               pszFullName,   
   NAME_MATCH           nameMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszFullName`  
 [in] 메서드 이름입니다.  
  
 `nameMatch`  
 [in] 형식을 일치, 예를 들어, 대/소문자 구분을 선택합니다.  
  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 이 메서드를 사용 하 여 연결 된 필드에 대 한 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 메서드 오버 로드를 예를 들어 경우 여러 필드를 사용 하 여 연결할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)