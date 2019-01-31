---
title: Windows API 함수를 디버그 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b177ec2664014fa547908aa18e19f605a83a8282
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931884"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Windows API 함수를 어떻게 디버깅할 수 있습니까?
NT 기호가 로드된 Windows API 함수를 디버깅하려면 다음 작업을 수행해야 합니다.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>NT 기호가 있는 Windows API 함수에 중단점을 설정하려면  
  
-   함수가 상주하는 DLL 이름과 함수 이름을 함께 입력합니다. 32비트 코드에서는 함수 이름의 데코레이팅된 형식을 사용합니다. 예를 들어 **MessageBeep**에 중단점을 설정하려면 다음을 입력해야 합니다.  
  
    ```cpp
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     데코레이팅된 이름을 가져오려면를 참조 하세요 [데코레이팅된 이름 보기](https://msdn.microsoft.com/library/f79e2717-a4db-4d12-a689-69830cce2be0)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)
