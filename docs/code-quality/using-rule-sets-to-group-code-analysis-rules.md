---
title: 코드 분석 규칙 집합
ms.date: 04/02/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c95b442835289265d197b6806c6d87fa051f2c1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62825086"
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>코드 분석 규칙 그룹화를 사용 하 여 규칙 집합

Visual Studio에서 코드 분석을 구성할 때 기본 제공 목록에서 선택할 수 있습니다 *규칙 집합*합니다. 규칙 집합은 대상된 문제 및 해당 프로젝트에 대 한 특정 조건을 식별 하는 코드 분석 규칙 그룹화 합니다. 예를 들어 공개적으로 사용 가능한 Api에 대 한 코드를 스캔 하도록 설계 된 규칙 집합을 적용할 수 있습니다. 또한 사용 가능한 모든 규칙을 포함 하는 규칙 집합을 적용할 수 있습니다.

규칙 경고 또는 오류를 표시할 추가 또는 삭제 규칙 또는 규칙 심각도 변경 하 여 집합을 사용자 지정할 수 있습니다 합니다 **오류 목록**합니다. 사용자 지정된 규칙 집합에는 특정 개발 환경의 요구 사항을 충족할 수 있습니다. 규칙 집합을 사용자 지정 규칙 집합 편집기 검색 및 필터링 프로세스에서 도움이 도구를 제공 합니다.

규칙 집합에 사용할 수 있는 [관리 되는 코드의 정적 분석](how-to-configure-code-analysis-for-a-managed-code-project.md)를 [분석 C++ 코드](using-rule-sets-to-specify-the-cpp-rules-to-run.md), 및 [Roslyn 분석기](analyzer-rule-sets.md).

## <a name="rule-set-format"></a>규칙 집합 형식

규칙 집합에 XML 형식으로 지정 된 *.ruleset* 파일입니다. ID가 구성 된 규칙 및 *동작*, 분석기 ID 및 파일에 네임 스페이스 별로 그룹화 됩니다.

콘텐츠를 *.ruleset* 이 XML 파일 비슷합니다.

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> 쉽습니다 [규칙 집합 편집](../code-quality/working-in-the-code-analysis-rule-set-editor.md) 에서 그래픽 **규칙 집합 편집기** 손으로 보다 합니다.

## <a name="specify-a-rule-set-for-a-project"></a>프로젝트에 대해 설정 하는 규칙 지정

규칙 집합으로 지정 된 프로젝트에 대 한 합니다 **CodeAnalysisRuleSet** Visual Studio 프로젝트 파일의 속성입니다. 예를 들어:

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

## <a name="see-also"></a>참고자료

- [코드 분석 규칙 집합 참조](../code-quality/rule-set-reference.md)