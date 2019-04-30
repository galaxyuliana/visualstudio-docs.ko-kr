---
title: IDebugCustomAttributeQuery::IsCustomAttributeDefined | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery::IsCustomAttributeDefined
- IsCustomAttributeDefined
ms.assetid: c7425db6-4347-4f69-8f88-337ddaa34fa6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 392067356cdc50b55ddf99b7342d76e1dcd02b09
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62568462"
---
# <a name="idebugcustomattributequeryiscustomattributedefined"></a>IDebugCustomAttributeQuery::IsCustomAttributeDefined
지정된 된 사용자 지정 특성은 정의 된 경우를 결정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsCustomAttributeDefined(
    LPCOLESTR pszCustomAttributeName
);
```

```csharp
int IsCustomAttributeDefined(
    string pszCustomAttributeName
);
```

#### <a name="parameters"></a>매개 변수
`pszCustomAttributeName`

 [in] 사용자 지정 특성의 이름입니다.

## <a name="return-value"></a>반환 값
사용자 지정 특성에 정의 된 경우 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE`합니다.

## <a name="example"></a>예제
다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **CDebugClassFieldSymbol** 노출 하는 개체를 [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md) 인터페이스입니다.

```cpp
HRESULT CDebugClassFieldSymbol::IsCustomAttributeDefined(
    LPCOLESTR pszCustomAttribute
)
{
    HRESULT hr = S_FALSE;
    CComPtr<IMetaDataImport> pMetadata;
    mdToken token = mdTokenNil;
    CComPtr<IDebugField> pField;
    CComPtr<IDebugCustomAttributeQuery> pCA;

    ASSERT(IsValidWideStringPtr(pszCustomAttribute));

    METHOD_ENTRY( CDebugClassFieldSymbol::IsCustomAttributeDefined );

    IfFalseGo( pszCustomAttribute, E_INVALIDARG );

    IfFailGo( m_spSH->GetMetadata( m_spAddress->GetModule(), &pMetadata ) );

    IfFailGo( CDebugCustomAttribute::GetTokenFromAddress( m_spAddress, &token) );
    IfFailGo( pMetadata->GetCustomAttributeByName( token,
              pszCustomAttribute,
              NULL,
              NULL ) );
Error:

    METHOD_EXIT( CDebugClassFieldSymbol::IsCustomAttributeDefined, hr );

    if (hr != S_OK)
    {
        hr = S_FALSE;
    }

    return hr;
}
```

## <a name="see-also"></a>참고 항목
- [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)
