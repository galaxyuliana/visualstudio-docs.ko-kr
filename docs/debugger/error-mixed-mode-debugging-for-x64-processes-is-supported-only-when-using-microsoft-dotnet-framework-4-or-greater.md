---
title: '오류: 혼합 모드 디버깅 프로세스는 Microsoft.NET Framework 4를 사용 하는 경우에 지원 됩니다 x64 이상 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 61c92460976ec9b95163b83744ee0b01b6ebc572
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986087"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>오류: x64 프로세스용 혼합 모드 디버깅은 Microsoft .NET Framework 4 이상을 사용할 때만 지원됩니다.
64비트 프로세스의 혼합 네이티브 및 관리 코드를 디버깅하려면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전 4가 있어야 합니다. 4 이전 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서는 64비트 프로세스의 혼합 모드 디버깅이 지원되지 않습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 다음 단계 중 하나를 수행합니다.  
  
  - [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 버전 4로 업그레이드합니다.  
  
  - 디버깅을 위해 32비트 버전의 응용 프로그램을 빌드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Remote Debugging](../debugger/remote-debugging.md)