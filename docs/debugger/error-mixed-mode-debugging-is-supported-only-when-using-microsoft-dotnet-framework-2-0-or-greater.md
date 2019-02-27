---
title: '오류: 혼합된 모드 디버깅은 Microsoft.NET Framework 2.0을 사용 하는 경우에 이상을 지원 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
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
ms.openlocfilehash: 2fb4d0dfaeb944700757c9ceec222dbd62dab9dd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681155"
---
# <a name="error-mixed-mode-debugging-is-supported-only-when-using-microsoft-net-framework-20-or-greater"></a>오류: 혼합 모드 디버깅은 Microsoft .NET Framework 2.0 이상을 사용할 때만 지원됩니다.
네이티브 코드와 관리 코드가 혼합된 코드를 디버깅하려면 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전 2.0, 3.0, 3.5 또는 4가 필요합니다. 이전 버전 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 사용한 혼합 모드 디버깅은 지원되지 않습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 버전 2.0, 3.0, 3.5 또는 4로 업그레이드합니다.

## <a name="see-also"></a>참고 항목
- [Remote Debugging](../debugger/remote-debugging.md)