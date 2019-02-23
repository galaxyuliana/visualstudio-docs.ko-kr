---
title: IDebugExtendedField::IsClosedType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9056a3543de27b26bc32eec5840248c337ea11fa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678334"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
필드 닫힌된 형식을 나타내는지 여부를 확인 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsClosedType(
   void
);
```

```csharp
int IsClosedType();
```

## <a name="return-value"></a>반환 값
 필드에 닫힌된 형식이 면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE`합니다.

## <a name="see-also"></a>참고 항목
- [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)