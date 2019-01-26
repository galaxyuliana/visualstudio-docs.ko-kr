---
title: IDebugEngine3::LoadSymbols | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::LoadSymbols
helpviewer_keywords:
- IDebugEngine3::LoadSymbols
ms.assetid: c846a440-1d91-4d48-b8f1-82e902ae152b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 704c11fb4af909f79969e86b901a4e51674c6f8c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043507"
---
# <a name="idebugengine3loadsymbols"></a>IDebugEngine3::LoadSymbols
이 디버깅 엔진으로 디버깅 중인 모든 모듈에 대 한 기호 (필요한 경우)으로 로드 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadSymbols();  
```  
  
```csharp  
int LoadSymbols();  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이이 디버깅 엔진에 의해 참조 되는 모든 모듈에 대 한 디버깅 기호를 로드 합니다. 기호는 이미 아직 로드 되지 않은 경우에 로드 됩니다. 기호를 호출 하 여 설정 경로에서 검색 됩니다 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)