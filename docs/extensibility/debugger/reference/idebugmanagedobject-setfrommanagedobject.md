---
title: IDebugManagedObject::SetFromManagedObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: dbaaf27222754d4a68d7de6367a2c0d7a1a8be73
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210622"
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
매개 변수로 제공 하는 값 클래스의 인스턴스에서 값 클래스 개체의 인스턴스 값을 설정 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SetFromManagedObject( 
   IUnknown* pManagedObject
);
```

```csharp
int SetFromManagedObject(
   object pManagedObject
);
```

## <a name="parameters"></a>매개 변수
`pManagedObject`\
[in] 새 값이 포함 된 관리 되는 개체를 나타내는 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 에 표시 된 대로 관리 되는 개체를 변경 하려면이 메서드는 사용 된 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) 개체입니다.

## <a name="see-also"></a>참고자료
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)