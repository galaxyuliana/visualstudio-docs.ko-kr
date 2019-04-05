---
title: IDebugPropertyField | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPropertyField
helpviewer_keywords:
- IDebugPropertyField interface
ms.assetid: b50edb2c-fb8d-4def-993d-17d23d2027c1
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b552db33c40b9ecdeca9761658704ec0baaa8eb5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58986027"
---
# <a name="idebugpropertyfield"></a>IDebugPropertyField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스는 가져오고 속성을 설정할 수 있는 함수를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPropertyField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 합니다 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)합니다. 이 인터페이스는 클래스에서 속성의 개념을 지 원하는 특수화입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 사용 하 여 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 에서이 인터페이스를 가져올 수 합니다 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 메서드가 반환 되는 `FIELD_KIND_PROP`합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 합니다 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스에서이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)|속성을 가져오는 메서드를 가져옵니다.|  
|[GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)|속성을 설정 하는 메서드를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 속성은 관리 코드 개념 및 변수로 처리 되는 메서드를 나타냅니다. 속성은 관리 되지 않는 c + +에서 존재 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
