---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: 5
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ec541b6dc4ccae57628d4b33e7c188008da6edae
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60064039"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 사용자는 안전 하지 않은 프로세스에 연결 하려면 먼저 경고를 표시 하려면 포트 공급자를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 값은 아래와 같습니다.  
  
- `S_OK`: 프로세스에 연결 하는 것이 안전 하 고 경고 대화 상자가 표시 됩니다.  
  
- `S_FALSE`: 연결 보안 문제가 될 수 하 고 경고 대화 상자가 표시 됩니다.  
  
- `FAILURE`: 프로세스에 연결 실패 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
