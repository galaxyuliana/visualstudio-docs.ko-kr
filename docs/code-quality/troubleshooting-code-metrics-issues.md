---
title: 코드 메트릭 문제 해결
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3d4e83d264e474a8ff578d1b832c4c2a2484bcd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54937076"
---
# <a name="troubleshooting-code-metrics-issues"></a>코드 메트릭 문제 해결
코드 메트릭을 수집할 때 다음 문제 중 일부가 발생할 수 있습니다.

-   [Visual Studio 2010 코드 복잡성 계산에 대한 변경 내용](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>Visual Studio 2010 코드 복잡성 계산에 대한 변경 내용
 동일한 함수의 경우 다음 상황에서 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 계산 된 코드 복잡성 메트릭이 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]의 이전 버전으로 계산된 메트릭과 다를 수 있습니다.

- 이 함수는 하나 이상의 catch 블록을 포함합니다. [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]의 이전 버전에서 catch 블록은 계산에 포함되지 않았습니다. [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 각 catch 블록의 복잡성은 함수의 복잡성에 추가됩니다.

- 함수는 switch 문(VB에서 Select Case)을 포함합니다. [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]과 이전 버전 간의 컴파일러 차이점은 제어 이동 사례가 포함된 일부 switch 문에 대해 서로 다른 MSIL 코드를 생성할 수 있습니다.

## <a name="see-also"></a>참고 항목
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/code-metrics-values.md)