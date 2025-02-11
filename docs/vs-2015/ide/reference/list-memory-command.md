---
title: 메모리 목록 표시 명령 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 884dda624d5405ec017b544afd223be0bebc97e9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199162"
---
# <a name="list-memory-command"></a>메모리 목록 표시 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

지정된 메모리 범위의 내용을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]  
[/Hex|Signed|Unsigned] [expression]  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 선택 사항입니다. 메모리를 표시하기 시작할 메모리 주소입니다.  
  
## <a name="switches"></a>스위치  
 /ANSI&#124;Unicode  
 선택 사항입니다. 메모리에 해당하는 문자(ANSI 또는 유니코드)로 메모리를 표시합니다.  
  
 /Count:`number`  
 선택 사항입니다. `expression`에서 시작하여 표시할 메모리의 바이트 수를 결정합니다.  
  
 /Format:`formattype`  
 선택 사항입니다. **메모리** 창에서 메모리 정보를 볼 형식(OneByte, TwoBytes, FourBytes, EightBytes, Float(32비트) 또는 Double(64비트))을 지정합니다. OneByte를 사용하는 경우 `/Unicode`를 사용할 수 없습니다.  
  
 /Hex&#124;Signed&#124;Unsigned  
 선택 사항입니다. 서명됨, 서명하지 않음 또는 16진수로 숫자를 볼 형식을 지정합니다.  
  
## <a name="remarks"></a>설명  
 모든 스위치를 포함한 전체 **Debug.ListMemory** 명령을 작성하는 대신 특정 스위치를 지정된 값으로 미리 설정한 미리 정의된 별칭을 사용하여 명령을 호출할 수 있습니다. 예를 들어, 다음을 입력하는 대신  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
 다음과 같이 작성할 수 있습니다.  
  
```  
>df /Count:30 /Unicode  
```  
  
 **Debug.ListMemory** 명령에 사용할 수 있는 별칭 목록은 다음과 같습니다.  
  
|Alias|명령 및 스위치|  
|-----------|--------------------------|  
|**d**|Debug.ListMemory|  
|**da**|Debug.ListMemory /Ansi|  
|**db**|Debug.ListMemory /Format:OneByte|  
|**dc**|Debug.ListMemory /Format:FourBytes /Ansi|  
|**dd**|Debug.ListMemory /Format:FourBytes|  
|**df**|Debug.ListMemory /Format:Float|  
|**dq**|Debug.ListMemory /Format:EightBytes|  
|**du**|Debug.ListMemory /Unicode|  
  
## <a name="example"></a>예  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
## <a name="see-also"></a>참고 항목  
 [호출 스택 목록 표시 명령](../../ide/reference/list-call-stack-command.md)   
 [스레드 목록 표시 명령](../../ide/reference/list-threads-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
