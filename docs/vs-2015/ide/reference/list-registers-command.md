---
title: 레지스터 목록 표시 명령 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6f9eaa1299ec49cf20713723e822f8fc641401d8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199132"
---
# <a name="list-registers-command"></a>레지스터 목록 표시 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

선택된 레지스터의 값을 등록하고 표시할 레지스터의 목록을 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>스위치  
 /Display [{`register`&#124;`registerGroup`}...]  
 지정된 `register` 또는 `registerGroup`의 값을 표시합니다. `register` 또는 `registerGroup`를 지정하지 않은 경우 레지스터의 기본 목록이 표시됩니다. 스위치를 지정하지 않은 경우 동작은 동일합니다. 예를 들어:  
  
 `Debug.ListRegisters /Display eax`  
  
 위의 식은 아래의 식과 동일합니다.  
  
 `Debug.ListRegisters eax`  
  
 /List  
 목록에서 레지스터 그룹을 모두 표시합니다.  
  
 /Watch [{`register`&#124;`registerGroup`}...]  
 하나 이상의 `register` 또는 `registerGroup` 값을 목록에 추가합니다.  
  
 /Unwatch [{`register`&#124;`registerGroup`}...]  
 하나 이상의 `register` 또는 `registerGroup` 값을 목록에서 제거합니다.  
  
## <a name="remarks"></a>설명  
 별칭 `r`을 `Debug.ListRegisters` 대신 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Debug.ListRegisters` 별칭 `r`을 사용하여 `Flags` 레지스터 그룹의 값을 표시합니다.  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>관련 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [디버깅 기본 사항: 레지스터 창](../../debugger/debugging-basics-registers-window.md)   
 [방법: 레지스터 창 사용](../../debugger/how-to-use-the-registers-window.md)
