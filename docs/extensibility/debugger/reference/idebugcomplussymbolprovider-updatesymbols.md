---
title: IDebugComPlusSymbolProvider::UpdateSymbols | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- UpdateSymbols
- IDebugComPlusSymbolProvider::UpdateSymbols
ms.assetid: d530f6f1-4af2-454b-bab0-02478a8fe81e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6c3c396dbea0e005012162080590a0b84ec9f5b
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413295"
---
# <a name="idebugcomplussymbolproviderupdatesymbols"></a>IDebugComPlusSymbolProvider::UpdateSymbols
지정 된 데이터 스트림에서 메모리의 디버그 기호를 업데이트합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT UpdateSymbols (
    ULONG32  ulAppDomainID,
    GUID     guidModule,
    IStream* pUpdateStream
);
```

```csharp
int UpdateSymbols (
    uint    ulAppDomainID,
    Guid    guidModule,
    IStream pUpdateStream
);
```

#### <a name="parameters"></a>매개 변수
`ulAppDomainID`  
[in] 응용 프로그램 도메인의 식별자입니다.

`guidModule`  
[in] 모듈의 고유 식별자입니다.

`pUpdateStream`  
[in] 업데이트 된 디버그 기호를 포함 하는 데이터 스트림.

## <a name="example"></a>예제
다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **CDebugSymbolProvider** 노출 하는 개체를 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) 인터페이스입니다.

```cpp
HRESULT CDebugSymbolProvider::UpdateSymbols(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IStream* pUpdateStream
)
{
    ASSERT(!"Use UpdateSymbols2 on IDebugENCSymbolProvider2");
    return E_NOTIMPL;
}

HRESULT CDebugSymbolProvider::UpdateSymbols2(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IStream* pUpdateStream,
    LINEDELTA* pDeltaLines,
    ULONG cDeltaLines
)
{
    HRESULT hr = S_OK;
    CComPtr<CModule> pModule;
    Module_ID idModule(ulAppDomainID, guidModule);

    METHOD_ENTRY( CDebugSymbolProvider::UpdateSymbols );

    IfFailGo( GetModule( idModule, &pModule ) );
    IfFailGo( pModule->UpdateSymbols( pUpdateStream, pDeltaLines, cDeltaLines ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::UpdateSymbols, hr );

    return hr;
}
```

## <a name="return-value"></a>반환 값
성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
