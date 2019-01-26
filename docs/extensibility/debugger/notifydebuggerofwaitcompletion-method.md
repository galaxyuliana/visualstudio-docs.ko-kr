---
title: NotifyDebuggerOfWaitCompletion 메서드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 29657a85b72fa57f37a3932465b5aeb874e9a672
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012393"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion 메서드
디버거에서 중단점 대상으로 사용 된 자리 표시자 메서드. 이 메서드가 인라인 또는 최적화 된 아니어야 합니다.  
  
 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (에서 *mscorlib.dll*)  
  
## <a name="syntax"></a>구문  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>설명  
 작업을 사용 하 여 모든 조인 연산이 해당 디버거 알림 비트가 설정 되 면이 메서드를 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="see-also"></a>참고자료  
 [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)