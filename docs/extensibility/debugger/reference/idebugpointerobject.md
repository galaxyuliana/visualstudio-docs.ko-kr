---
title: IDebugPointerObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject
helpviewer_keywords:
- IDebugPointerObject interface
ms.assetid: 257fa167-b46e-4ffb-9a12-272efbf26702
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db0122ab12d74f6a4dd2885671067dcfe5f3254f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63413501"
---
# <a name="idebugpointerobject"></a>IDebugPointerObject
> [!IMPORTANT]
> Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.

 이 인터페이스에 대 한 포인터를 나타냅니다.

## <a name="syntax"></a>구문

```
IDebugPointerObject : IDebugObject
```

## <a name="notes-for-implementers"></a>구현자 참고 사항
 식 계산기는 포인터 개체를 나타내는 데이 인터페이스를 구현 합니다.

## <a name="notes-for-callers"></a>호출자에 대 한 정보
 합니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스를 사용 하 여이 인터페이스를 가져올 수 있습니다 [QueryInterface](/cpp/atl/queryinterface) 경우는 `IDebugObject` 포인터를 나타냅니다.

## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드
 상속 된 메서드 외에도 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugPointerObject` 인터페이스는 다음 메서드를 노출 합니다.

|메서드|설명|
|------------|-----------------|
|[Dereference](../../../extensibility/debugger/reference/idebugpointerobject-dereference.md)|인터페이스를 가리키는 개체를 가져옵니다.|
|[GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)|인터페이스를 가리키는 일련의 연속 된 바이트 값을 가져옵니다.|
|[SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)|인터페이스를 가리키는 일련의 연속 된 바이트 값을 설정 합니다.|

## <a name="remarks"></a>설명
 식 계산기를 구문 분석 트리에 대 한 포인터를 나타내는 데이 인터페이스를 사용 합니다.

## <a name="requirements"></a>요구 사항
 헤더: ee.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [식 계산 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)