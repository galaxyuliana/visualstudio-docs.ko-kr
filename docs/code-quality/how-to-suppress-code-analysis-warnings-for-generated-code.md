---
title: 생성 된 코드에 대 한 코드 분석 위반 표시 안 함
ms.date: 05/13/2019
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ee4e3df94e46b4d3cc996a23fc1e40401195e21
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551128"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>방법: 생성된 코드에 대한 코드 분석 경고 표시 안 함

생성 된 코드에는 관리 코드 컴파일러 또는 타사 도구를 통해 프로젝트에 추가 되는 코드가 포함 됩니다. 코드 분석이 생성 된 코드에서 검색 하는 규칙 위반을 확인 하는 것이 좋습니다. 그러나 위반을 포함 하는 코드를 보고 유지 관리할 수 없으므로 해당 코드를 표시 하지 않으려고 할 수 있습니다.

프로젝트의 코드 분석 속성 페이지에서 **생성 된 코드에서 결과 표시 안 함** 확인란을 사용 하면 타사 도구에 의해 생성 된 코드에서 코드 분석 경고를 표시할지 여부를 선택할 수 있습니다.

> [!NOTE]
> 이 옵션을 선택하더라도 폼 및 템플릿에 오류와 경고가 나타날 경우에는 생성된 코드에서 발생한 코드 분석 오류 및 경고가 계속 표시됩니다. 폼이나 템플릿의 소스 코드를 볼 수도 있고 유지 관리할 수도 있습니다.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>프로젝트에서 생성 된 코드에 대 한 경고를 표시 하지 않으려면

1. **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

2. **코드 분석** 탭을 선택 합니다.

3. 생성 된 **코드에서 결과 표시 안 함** 확인란을 선택 합니다.

> [!NOTE]
> 레거시 분석의 경고만 표시 하지 않을 수 있습니다. 현재 [분석기](roslyn-analyzers-overview.md)에서 코드 분석 경고를 표시 하지 않을 수 있습니다.