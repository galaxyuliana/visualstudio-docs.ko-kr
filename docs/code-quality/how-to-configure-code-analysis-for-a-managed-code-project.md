---
title: 코드 분석 구성
ms.date: 04/04/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
- vs.codeanalysis.propertypages.solution
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a17db8fbdb281139ba095070130e6c608954b5a7
ms.sourcegitcommit: 62f42113ae4dae1ddfff1c4e02445acc09913445
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64878179"
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>방법: 관리 코드 프로젝트에 대한 코드 분석 구성

Visual Studio에서 코드 분석의 목록에서 선택할 수 있습니다 [규칙 집합](../code-quality/rule-set-reference.md) 관리 코드 프로젝트에 적용 합니다. 기본적으로 **Microsoft 최소 권장 규칙** 규칙 집합 선택 되어 있지만 원하는 경우 설정 하는 다른 규칙을 적용할 수 있습니다. 솔루션의 프로젝트에 하나 이상의 규칙 집합을 적용할 수 있습니다.

> [!TIP]
> ASP.NET 웹 응용 프로그램에 대해 설정 하는 규칙을 구성 하는 방법에 대 한 정보를 참조 하세요. [방법: ASP.NET 웹 응용 프로그램에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)합니다.

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>.NET Framework 프로젝트에 대해 설정 하는 규칙을 구성 하려면

1. 엽니다는 **코드 분석** 프로젝트의 속성 페이지의 탭 합니다. 다음 방법 중 하나에서이 수행할 수 있습니다.

   - **솔루션 탐색기**, 프로젝트를 선택 합니다. 메뉴 모음에서 선택 **분석** > **코드 분석 구성** > **에 대 한 \<projectname >** 합니다.

   - 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **속성**를 선택한 후는 **코드 분석** 탭 합니다.

1. 에 **구성** 하 고 **플랫폼** 목록에서 빌드 구성과 대상 플랫폼을 선택 합니다.

1. 선택한 구성을 사용 하 여 프로젝트를 빌드할 때마다 코드 분석을 실행 하려면 선택 합니다 **빌드에 코드 분석 사용** 확인란 합니다. 선택 하 여 코드 분석을 수동으로 실행할 수도 있습니다 **분석** > **코드 분석 실행** > **에서 코드 분석 실행 \<projectname >**.

1. 기본적으로 외부 도구에 의해 자동으로 생성된 코드에서 발생한 경고는 코드 분석 시 보고되지 않습니다. 생성 된 코드에서 발생 한 경고를 보려면의 선택을 취소 합니다 **생성 된 코드 결과 표시 안 함** 확인란 합니다.

    > [!NOTE]
    > 이 옵션을 선택하더라도 폼 및 템플릿에 오류와 경고가 나타날 경우에는 생성된 코드에서 발생한 코드 분석 오류 및 경고가 계속 표시됩니다. 모두 보기를 덮어쓰는 것을 하지 않고도 폼 또는 템플릿을 소스 코드를 유지 관리 합니다.

1. 에 **이 규칙 집합 실행** 목록에서 다음 중 하나를 수행 합니다.

    - 사용 하려는 규칙 집합을 선택 합니다.

    - 선택  **\<찾아보기... >** 목록에 없는 기존 사용자 지정 규칙 집합을 찾을 하려면.

    - 정의 된 [사용자 지정 규칙 집합](../code-quality/how-to-create-a-custom-rule-set.md)합니다.

## <a name="specify-rule-sets-for-multiple-projects-in-a-solution"></a>솔루션의 여러 프로젝트에 대 한 규칙 집합 지정

기본적으로 솔루션의 관리 되는 모든 프로젝트는 할당 된 *Microsoft 최소 권장 규칙* 코드 분석 규칙 집합입니다. 솔루션의 프로젝트에 할당 되는 규칙 집합을 변경할 수 있습니다 합니다 **속성** 솔루션에 대 한 대화 상자.

1. Visual Studio에서 솔루션을 엽니다.

2. 에 **분석** 메뉴에서 **솔루션에 대 한 코드 분석 구성**합니다.

3. 필요한 경우 확장 **공용 속성**를 선택한 후 **코드 분석 설정**합니다.

4. 하나 이상의 프로젝트에 대해 설정 하는 규칙을 지정할 수 있습니다.

    - 개별 프로젝트에 대해 설정 하는 규칙을 지정 하려면 프로젝트 이름을 선택 합니다.

    - 여러 프로젝트를 설정 하는 규칙을 지정 하려면 누른 **Ctrl** 프로젝트 이름을 선택 합니다.

    - 솔루션의 모든 프로젝트를 지정 하려면 누른 **Shift** 프로젝트 목록에서 클릭 합니다.

5. 선택 된 **규칙 집합** 규칙의 이름을 적용 하려는 프로젝트의 필드 및 선택 설정 합니다.

## <a name="see-also"></a>참고 항목

- [코드 분석 규칙 집합 참조](../code-quality/rule-set-reference.md)
- [방법: ASP.NET 웹 응용 프로그램에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)
