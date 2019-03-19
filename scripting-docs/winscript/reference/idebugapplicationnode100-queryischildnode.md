---
title: IDebugApplicationNode100::QueryIsChildNode | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::QueryIsChildNode
ms.assetid: 4f36f435-0f34-4f9e-bba3-e75285fd7bbb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f620a5545c65683eaafd0ac457621f01e6782dff
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151104"
---
# <a name="idebugapplicationnode100queryischildnode"></a>IDebugApplicationNode100::QueryIsChildNode
지정된 된 문서가 노드의 자식 노드 중 하나에 속하는지 여부를 결정 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md) 이상 v10.0 PDM에서 구현 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryIsChildNode(        [in] IDebugDocument* pSearchKey        );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSearchKey`  
 검색 키입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md)