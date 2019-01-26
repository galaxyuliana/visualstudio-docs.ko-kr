---
title: IManagedAddin::Unload
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Unload method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 68ef36185c193263db386a1e1f80877c0327440c
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54874343"
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  관리되는 VSTO 추가 기능이 언로드되기 바로 전에 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```csharp
HRESULT Unload();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 버전의 Microsoft Office에서 호출되지 않습니다. @FSHO2@이 메서드는 나중에 사용할 수 있도록 예약되어 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [IManagedAddin 인터페이스](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
