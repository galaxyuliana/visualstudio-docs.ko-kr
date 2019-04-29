---
title: IDebugClassField::EnumBaseClasses | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 74889ed04dceb133c80467d20f723f9561b6e25c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922767"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
이 클래스의 기본 클래스에 대 한 열거자를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumBaseClasses( 
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumBaseClasses(
   out IEnumDebugFields ppEnum
);
```

#### <a name="parameters"></a>매개 변수
 `ppEnum`

 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 기본 클래스의 목록을 나타내는 개체입니다. 기본 클래스가 없고 없으면 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환, 기본 클래스가 없고 없으면 S_SH_NO_BASE_CLASSES를 반환 합니다 (및 `ppEnum` 매개 변수는 null 값으로 설정)이 고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 열거자 개체의 기본 클래스는 대부분의 원격 기본 클래스에 즉각적인 (또는 가장 많이 파생 된) 기본 클래스의 순서에 지정 됩니다. 예를 들어는 C++ 클래스:

```
class Root { }
class Level1 : Root { }
class Level2 : Level1 { }
class MyClass : Level2 { }
```

 열거형 기본 클래스를 순서 대로 반환 `Level2`, `Level1`, `Root`합니다.

## <a name="see-also"></a>참고 항목
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)