---
title: 솔루션 열기 명령 | Microsoft 문서
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bb99d359f3858d8e7f15e013ab56719c7ed14995
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59654609"
---
# <a name="open-solution-command"></a>솔루션 열기 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

기존 솔루션을 열고 다른 열려 있는 솔루션을 모두 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>인수  
 `Filename`  
 필수 요소. 열려는 솔루션의 전체 경로와 파일 이름입니다.  
  
 `filename` 인수 구문에서 공백을 포함하는 경로에는 따옴표를 사용해야 합니다.  
  
## <a name="remarks"></a>주의  
 입력 시 자동 완성에서 올바른 경로와 파일 이름을 찾으려고 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 Test1.sln 솔루션을 엽니다.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
