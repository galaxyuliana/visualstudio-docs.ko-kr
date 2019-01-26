---
title: IEEVisualizerService | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEEVisualizerService
helpviewer_keywords:
- IEEVisualizerService interface
ms.assetid: 3bdb124b-c582-47ba-b465-13c6a1cdb702
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30cc53b09d82ac762b48b5682b3c564695a984a2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022341"
---
# <a name="ieevisualizerservice"></a>IEEVisualizerService
> [!IMPORTANT]
>  Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스를 구현 하는 기능을 제공 하는 주요 메서드는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 하 고 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEEVisualizerService : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio (EE) 형식 시각화 도우미를 지원 하기 위해 식 계산기를 허용 하려면이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 EE 호출 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md) 형식 시각화 도우미에 대 한 지원의 일부로이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)|이 서비스에서 알 수에 대 한 사용자 지정 뷰어 수를 검색 합니다.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)|사용자 지정 뷰어에 목록을 검색합니다.|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)|속성에 대 한 프록시 개체를 반환합니다.|  
|[GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)|지정 된 속성 또는 필드에 대해 표시할 문자열 값을 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 IDE를 사용 합니다 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 모든 사용자 지정 뷰어가 있는지 확인 하는 인터페이스 또는 속성에 대 한 시각화 도우미 형식. 시각화 도우미 서비스를 만들어 (사용 하 여 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)), EE 하는 기능을 제공할 수는 `IDebugProperty3` 및 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) (보기 및 변경 지는 속성의 값) 인터페이스 및 있으므로 형식 시각화 도우미를 지원 합니다.  
  
 EE에 사용자 지정 뷰어 구현 그 자체가, EE 추가할 수는 `CLSID`반환한 목록 끝에 해당 사용자 지정 뷰어에 2!s [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)합니다. 이 EE를 형식 시각화 도우미 및 자체 사용자 지정 뷰어를 모두 지 원하는 수 있습니다. 방금 해야 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) 모든 사용자 지정 뷰어가의 추가 반영 합니다.  
  
 참조 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) 시각화 도우미 및 뷰어 간의 차이점에 대 한 내용은 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [식 계산 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)   
 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)