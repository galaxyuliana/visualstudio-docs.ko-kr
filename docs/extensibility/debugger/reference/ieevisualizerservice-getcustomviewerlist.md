---
title: IEEVisualizerService::GetCustomViewerList | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerService::GetCustomViewerList
helpviewer_keywords:
- IEEVisualizerService::GetCustomViewerList method
ms.assetid: 249d26ca-914f-43af-a400-8162477223f4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 00a7928b203d00e0f9b43250a463a8fb272ce755
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62915186"
---
# <a name="ieevisualizerservicegetcustomviewerlist"></a>IEEVisualizerService::GetCustomViewerList
이 메서드는이 서비스에서 인식 되는 형식 시각화 도우미의 목록을 반환 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCustomViewerList(
   ULONG                celtSkip,
   ULONG                celtRequested,
   DEBUG_CUSTOM_VIEWER* rgViewers,
   ULONG*               pceltFetched
);
```

```csharp
int GetCustomViewerList(
   uint                  celtSkip,
   uint                  celtRequested,
   DEBUG_CUSTOM_VIEWER[] rgViewers,
   out uint              pceltFetched
);
```

#### <a name="parameters"></a>매개 변수
 `celtSkip`

 [in] 시각화 도우미를 건너뛸 수 있습니다.

 `celRequested`

 [in] 시각화 도우미를 검색할 수 (또한의 크기를 지정 된 `rgViewers` 배열)입니다.

 `rgViewers`

 [out에서] 배열을 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 구조를 채울 수 있습니다.

 `pceltFetched`

 [out] 실제로 검색 하는 시각화 도우미의 수입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
- [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 형식 시각화 도우미에 대 한 지원의 일환으로이 메서드를 요청을 전달 합니다. 식 계산기는 동일한 형식에 대 한 사용자 지정 뷰어를 제공 하는 경우 입력 아웃 적절 하 게 추가할 수 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) 이러한 사용자 지정 뷰어 목록에 대 한 구조입니다. 했는지 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 이러한 추가 뷰어를 반영 합니다.

 참조 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) 시각화 도우미 및 뷰어 간의 차이점에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고 항목
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)
- [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)
- [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)
- [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)
- [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)