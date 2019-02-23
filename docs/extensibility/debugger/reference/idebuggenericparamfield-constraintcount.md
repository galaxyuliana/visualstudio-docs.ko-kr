---
title: IDebugGenericParamField::ConstraintCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ConstraintCount
- IDebugGenericParamField::ConstraintCount
ms.assetid: 76bef0cb-8a3c-4ce5-87cc-1809de229f33
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f21e872fc04bc3d18ca3c332622844bfc57ece67
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688916"
---
# <a name="idebuggenericparamfieldconstraintcount"></a>IDebugGenericParamField::ConstraintCount
이 제네릭 매개 변수를 사용 하 여 연결 된 제약 조건의 수를 반환 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT ConstraintCount(
    ULONG32* pcConst
);
```

```csharp
int ConstraintCount(
    ref uint pcConst
);
```

#### <a name="parameters"></a>매개 변수
`pcConst`

 [out에서] 이 필드와 연관 된 제약 조건 수입니다.

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="example"></a>예제
다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **CDebugGenericParamFieldType** 노출 하는 개체를 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md) 인터페이스입니다.

```cpp
HRESULT CDebugGenericParamFieldType::ConstraintCount(ULONG32* pcConst)
{
    HRESULT hr = S_OK;
    CComPtr<IMetaDataImport> pMetadata;
    CComPtr<IMetaDataImport2> pMetadata2;
    HCORENUM hEnum = 0;
    ULONG cConst = 0;

    METHOD_ENTRY( CDebugGenericParamFieldType::ConstraintCount );

    IfFalseGo(pcConst, E_INVALIDARG );
    *pcConst = 0;
    IfFailGo( m_spSH->GetMetadata( m_idModule, &pMetadata ) );
    IfFailGo( pMetadata->QueryInterface(IID_IMetaDataImport2, (void**)&pMetadata2) );
    IfFailGo( pMetadata2->EnumGenericParamConstraints( &hEnum,
              m_tokParam,
              NULL,
              0,
              &cConst) );
    IfFailGo( pMetadata->CountEnum(hEnum, &cConst) );
    pMetadata->CloseEnum(hEnum);
    hEnum = NULL;

    *pcConst = cConst;

Error:

    METHOD_EXIT( CDebugGenericParamFieldType::ConstraintCount, hr );
    return hr;
}
```

## <a name="see-also"></a>참고 항목
- [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)
