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
ms.openlocfilehash: 6a7990f5e9fa1893d8813b1307ab6a0a7fee46be
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65613564"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>방법: 생성된 코드에 대한 코드 분석 경고 표시 안 함

생성 된 코드는 관리 코드 컴파일러 또는 타사 도구에서 프로젝트에 추가 되는 코드를 포함 합니다. 생성 된 코드에서 코드 분석을 검색 하는 규칙 위반을 확인 하려는 합니다. 그러나 보기 위반을 포함 하는 코드를 유지 관리할 수 없습니다 때문에 볼 하려는 없습니다.

합니다 **생성 된 코드 결과 표시 안 함** 프로젝트의 코드 분석 속성 페이지에서 확인란을 사용 하면 코드 분석 경고는 타사 도구에서 생성 된 코드를 표시할지 여부를 선택할 수 있습니다.

> [!NOTE]
> 이 옵션을 선택하더라도 폼 및 템플릿에 오류와 경고가 나타날 경우에는 생성된 코드에서 발생한 코드 분석 오류 및 경고가 계속 표시됩니다. 폼이나 템플릿의 소스 코드를 볼 수도 있고 유지 관리할 수도 있습니다.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>프로젝트에서 생성 된 코드에 대 한 경고를 표시 하지 않으려면

1. 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 을 클릭 한 다음 **속성**합니다.

2. 선택 된 **코드 분석** 탭 합니다.

3. 선택 된 **생성 된 코드 결과 표시 안 함** 확인란 합니다.

> [!NOTE]
> 정적 코드 분석에서 경고 표시 하지 않을 수 있습니다. 코드 분석 경고를 표시 하지 않을 수 없습니다. 현재 [분석기](roslyn-analyzers-overview.md)합니다.