---
title: IEEVisualizerService::GetValueDisplayStringCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IEEVisualizerService::GetValueDisplayStringCount
- GetValueDisplayStringCount
ms.assetid: d683a833-fbfb-4042-84df-6905124a268a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e401e009cd4119704e72dec09614ec013aa9eee0
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223554"
---
# <a name="ieevisualizerservicegetvaluedisplaystringcount"></a>IEEVisualizerService::GetValueDisplayStringCount
지정 된 속성 또는 필드에 대해 표시할 문자열 값을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetValueDisplayStringCount (
   DWORD         displayKind,
   IDebugField * propertyOrField,
   ULONG *       pcelt
);
```

```csharp
int GetValueDisplayStringCount (
   uint        displayKind,
   IDebugField propertyOrField,
   out ulong   pcelt
);
```

## <a name="parameters"></a>매개 변수
 `displayKind`\

 [in] 값을 [DisplayKind](../../../extensibility/debugger/reference/displaykind.md) 열거형입니다.

 `propertyOrField`\

 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 속성 또는 필드를 나타내는 인터페이스입니다.

 `pcelt`\

 [out] 표시할 문자열 값의 수를 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)