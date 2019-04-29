---
title: IDebugCustomAttributeQuery2::IsCustomAttributeDefined | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
ms.assetid: 5c07cc52-6d2d-42df-9d76-9f1f769641db
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6695753fa1b071f8623b079dbe4e56e68e9dfad4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62876026"
---
# <a name="idebugcustomattributequery2iscustomattributedefined"></a>IDebugCustomAttributeQuery2::IsCustomAttributeDefined
사용자 지정 특성을 이름별 있는지 여부를 결정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsCustomAttributeDefined( 
   LPCOLESTR pszCustomAttributeName
);
```

```csharp
int IsCustomAttributeDefined(
   [In] string pszCustomAttributeName
);
```

#### <a name="parameters"></a>매개 변수
 `pszCustomAttributeName`

 [in] 검색할 사용자 지정 특성의 이름을 포함 하는 문자열입니다.

## <a name="return-value"></a>반환 값
 S_ok이 고, 사용자 지정 특성은이 필드에 정의 되어 있으면 그렇지 S_FALSE를 반환 합니다.

## <a name="remarks"></a>설명
 사용자 지정 특성을 사용 하 여 연결 된 특성 바이트를 가져오려면 호출 합니다 [GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)