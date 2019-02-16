---
title: BUILT_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BUILT_TYPE
helpviewer_keywords:
- BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 692391379c3f2581e535a9e5c885f776565fb93d
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315488"
---
# <a name="builttype"></a>BUILT_TYPE
이 구조체는 메타 데이터에서 가져온 필드 형식에 대 한 정보를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct _tagTYPE_BUILT {
    ULONG32      ulAppDomainID;
    GUID         guidModule;
    IDebugField* pUnderlyingField;
} BUILT_TYPE;
```

```csharp
public struct BUILT_TYPE {
    public uint        ulAppDomainID;
    public Guid        guidModule;
    public IDebugField pUnderlyingField;
};
```

#### <a name="parameters"></a>매개 변수
ulAppDomainID  
기호 가져온 응용 프로그램의 ID입니다. 이 응용 프로그램의 인스턴스를 고유 하 게 식별에 사용 됩니다.

guidModule  
이 필드를 포함 하는 모듈의 GUID입니다.

pUnderlyingField  
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 이 기본 제공된 필드와 연결 된 기본 필드를 식별 하는 개체입니다.

## <a name="remarks"></a>설명
이 구조체의 공용 구조체의 일부분으로 표시를 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) 경우 구조체를 `dwKind` 필드를 `TYPE_INFO` 구조로 설정 되어 `TYPE_KIND_BUILT` (의 값을 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) 열거형)입니다.

## <a name="requirements"></a>요구 사항
헤더: sh.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)  
[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)  
[dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)  
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
