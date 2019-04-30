---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 59506af5ad48bd18c454f4c59367921eed1e679a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924079"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
이 별칭을 사용 하 여 연결 된 값을 나타내는 관리 코드 인터페이스를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

#### <a name="parameters"></a>매개 변수
 `ppUnk`

 [out] `IUnknown` 이 별칭을 사용 하 여 연결 된 값을 나타내는 인터페이스입니다. 이 인터페이스를 쿼리할 수는 `ICorDebugValue` 인터페이스입니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 이 메서드는 관리 되는 값에만 적용 됩니다 (합니다 `ICorDebugValue` 은 인터페이스에서 사용할 수 있는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] 에 정의 된는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] cordebug.idl 파일에서 SDK).

## <a name="see-also"></a>참고 항목
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)