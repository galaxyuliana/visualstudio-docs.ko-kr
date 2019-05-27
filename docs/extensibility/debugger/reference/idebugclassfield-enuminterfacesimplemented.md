---
title: IDebugClassField::EnumInterfacesImplemented | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 74a1de38344b8570df0b5381842be508e45c5fdb
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203206"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
이 클래스에서 구현 된 인터페이스에 대 한 열거자를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumInterfacesImplemented( 
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumInterfacesImplemented(
   out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>매개 변수
`ppEnum`\
[out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 구현 된 인터페이스의 목록을 나타내는 개체입니다. 인터페이스가 없는 경우 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 또는이 클래스에서 구현 된 인터페이스가 없는 경우 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="remarks"></a>설명
 열거형의 각 요소는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 인터페이스를 설명 하는 개체입니다. 관리 되지 않는 보면 [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] 코드 사용 하지 않으므로 인터페이스 불연속 엔터티로 관리 되지 않는 한 항상이 메서드가 null 값을 반환 [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] 코드입니다.

## <a name="see-also"></a>참고자료
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)