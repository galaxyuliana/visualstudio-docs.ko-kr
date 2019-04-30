---
title: IPropertyProxyProvider::GetPropertyProxy | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyProvider::GetPropertyProxy
helpviewer_keywords:
- IPropertyProxyProvider::GetPropertyProxy
ms.assetid: 3ebb7515-5bfe-48f4-9b8d-721b8f664eb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44a267b39ab630646803165a31f01b0bb4b45f47
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865812"
---
# <a name="ipropertyproxyprovidergetpropertyproxy"></a>IPropertyProxyProvider::GetPropertyProxy
지정 된 프록시 ID에 대 한 속성 프록시 인터페이스를 검색합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetPropertyProxy(
   DWORD                  dwID,
   IPropertyProxyEESide** proxy
);
```

```csharp
int GetPropertyProxy(
   uint                     dwID,
   out IPropertyProxyEESide proxy
);
```

#### <a name="parameters"></a>매개 변수
 `dwID`

 [in] Desired 속성 프록시의 ID입니다.

 `proxy`

 [out] 반환 된 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 외부 형식 시각화 도우미를 지원 하려면이 방법을 일반적으로 호출을 전달 합니다 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md) 메서드. 참조 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 는 IEEVisualizerService 가져온 방법에 대 한 내용은 합니다.

## <a name="see-also"></a>참고 항목
- [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)
- [데이터 시각화 및 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)