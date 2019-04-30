---
title: IDebugBinder3::GetTypeArguments | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7cbccb155b8a96a3a7480c4e898a597e57250df4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923658"
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
이 메서드는이 개체와 연결 된 인수 형식 목록을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetTypeArguments(
   UINT          skip,
   UINT          count,
   IDebugField** ppFields,
   UINT*         pFetched
);
```

```csharp
int GetTypeArguments(
   uint          skip,
   uint          count,
   IDebugField[] ppFields,
   out uint      pFetched
);
```

#### <a name="parameters"></a>매개 변수
 `skip`

 [in] 인수 형식 가져오기 전에 건너뛸 필드 수입니다.

 `count`

 [in] 반환할 인수 필드 수 (도의 크기를 지정 된 `ppFields` 배열)입니다.

 `ppFields`

 [out에서] 이 메서드는 반환 시 채울 수 있는 필드의 배열입니다.

 `pFetched`

 [out] \(선택 사항) 인수 개수는 실제로 반환 된 필드를 입력 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 된 수의 인수 형식 미리 얻을 수 있습니다 [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)합니다.

## <a name="see-also"></a>참고 항목
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)