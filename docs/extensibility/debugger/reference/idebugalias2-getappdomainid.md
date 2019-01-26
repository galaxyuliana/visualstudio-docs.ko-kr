---
title: IDebugAlias2::GetAppDomainId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetAppDomainId
- IDebugAlias2::GetAppDomainId
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b70b26cbf9248f654836a2d138ad0f79b80a3b54
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011751"
---
# <a name="idebugalias2getappdomainid"></a>IDebugAlias2::GetAppDomainId
응용 프로그램 도메인에 대 한 식별자를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAppDomainId (  
   ULONG32* pappDomainId  
);  
```  
  
```csharp  
int GetAppDomainId (  
   out uint pappDomainId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pappDomainId`  
 [out] 응용 프로그램 도메인 식별자를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 응용 프로그램 다시 시작 될 때마다 응용 프로그램 도메인 식별자 변경 및 새 응용 프로그램 도메인 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)