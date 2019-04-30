---
title: '오류: Microsoft Visual Studio 원격 디버깅 모니터 원격 컴퓨터의 다른 사용자로 실행 중인지 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7cba3de8aa07a021d61e1ebb2a2c97f568eaf9ee
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388432"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 다른 사용자로 실행 중입니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

원격으로 디버깅할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 다른 사용자로 실행 중입니다.  
  
## <a name="cause"></a>원인  
 이 메시지는 인증 안 함 모드에서 디버깅할 때 msvsmon을 시작한 사용자와 Visual Studio를 실행하는 사용자가 서로 다른 경우에 나타납니다.  
  
## <a name="solution"></a>솔루션  
 가장 안전한 최상의 해결책은 Visual Studio와 동일한 사용자 계정에서 원격 디버깅 모니터(msvsmon.exe)를 실행하는 것입니다. 이렇게 할 수 없는 경우 원격 디버깅 모니터 **옵션** 대화 상자에서 **모든 사용자가 디버깅할 수 있도록 허용** 옵션을 선택하여 다른 계정에서 원격 디버깅 모니터를 실행할 수 있습니다.  
  
> [!CAUTION]
> 다른 사용자에게 연결 권한을 부여하면 잘못된 원격 디버깅 세션에 실수로 연결할 가능성이 있습니다. **인증 안 함** 모드에서 디버깅하는 것은 안전하지 않으므로 이 모드를 사용할 때는 특히 주의해야 합니다.  
  
 자세한 내용은 [원격 디버깅 모니터 시작](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)
