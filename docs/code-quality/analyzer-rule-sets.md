---
title: 분석기 규칙 집합
ms.date: 07/20/2018
ms.topic: conceptual
helpviewer_keywords:
- analyzers, rule sets
- rule sets for analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da5eab1424ac6f6fe580ec0f71ec3efd6e120020
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57866999"
---
# <a name="rule-sets-for-roslyn-analyzers"></a>Roslyn 분석기에 대 한 규칙 집합

미리 정의 된 규칙 집합은 일부 NuGet 분석기 패키지에 포함 합니다. 규칙 집합에 포함 된 예를 들어 합니다 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) NuGet 분석기 패키지 (버전 2.6.2부터) 이름 지정, 보안과 같은 해당 범주를 기반으로 하는 규칙을 사용할지 또는 성능을 제공 합니다. 규칙 집합을 사용 하 여 쉽게 신속 하 게만 규칙의 특정 범주에 속하는 해당 규칙 위반을 볼 수 있습니다.

Roslyn 분석기를 레거시 "FxCop" 정적 코드 분석에서 마이그레이션하는, 하는 경우 이러한 규칙 집합을 사용 하면 이전에 사용한 동일한 규칙 구성을 사용 하 여 계속 수 있습니다.

## <a name="use-analyzer-rule-sets"></a>분석기 규칙 집합 사용

한 후 [NuGet 분석기 패키지를 설치](install-roslyn-analyzers.md), 미리 정의 된 규칙 집합을 찾아 해당 *ruleset* 예를 들어 디렉터리 *% USERPROFILE %\\.nuget\packages\ microsoft.codequality.analyzers\<버전 > \rulesets*합니다. 여기에서 있습니다 수, 또는 복사 끌어서 이상의 ruleset Visual Studio 프로젝트에 붙여 넣습니다 **솔루션 탐색기**합니다.

프로젝트를 마우스 오른쪽 단추로 활성 규칙 집합 분석을 위해 설정 하는 규칙을 만들려면 **솔루션 탐색기** 선택한 **속성**합니다. 프로젝트 속성 페이지에서 선택 합니다 **코드 분석** 탭 합니다. 아래 **이 규칙 집합 실행**를 선택 **찾아보기**를 선택한 다음 프로젝트 디렉터리에 복사 하는 원하는 규칙 집합입니다. 이제 선택한 규칙 집합에서 사용 되는 규칙에 대 한 규칙 위반만 참조 합니다.

할 수도 있습니다 [미리 정의 된 규칙 집합을 사용자 지정](how-to-create-a-custom-rule-set.md#create-a-custom-rule-set) 을 원하는 대로 합니다. 예를 들어, 위반 오류 또는 경고에 표시 되도록 하나 이상의 규칙의 심각도 변경할 수 있습니다 합니다 **오류 목록**합니다.

## <a name="available-rule-sets"></a>사용 가능한 규칙 집합

패키지의 모든 규칙에 영향을 주는 세 가지 규칙 집합을 포함 하는 미리 정의 된 분석기 규칙 집합&mdash;모두를 사용 하도록 설정 하는 것을 모두 사용 하지 않도록 설정 하는, 하나는 각 규칙의 기본 심각도 및 사용 설정을 준수 하는:

- AllRulesEnabled.ruleset
- AllRulesDisabled.ruleset
- AllRulesDefault.ruleset

또한 각 범주의 성능 또는 보안과 같은 패키지에 대 한 규칙에 대 한 두 규칙 집합이 있습니다. 하나의 규칙 집합 범주에 대 한 모든 규칙 있으며 하나의 규칙 집합 범주에 각 규칙에 대 한 기본 심각도 및 사용 설정을 따릅니다.

합니다 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) NuGet 분석기 패키지는 일치 하는 규칙 집합 레거시 "FxCop" 정적 코드 분석에 사용할 수 있는 다음 범주에 대 한 규칙 집합에 포함 합니다.

- 디자인
- 문서
- 유지 관리
- 명명
- 성능
- 안정성
- 보안
- 사용법

## <a name="see-also"></a>참고자료

- [분석기 FAQ](analyzers-faq.md)
- [.NET Compiler Platform 분석기 개요](roslyn-analyzers-overview.md)
- [분석기를 설치 합니다.](install-roslyn-analyzers.md)
- [분석기를 사용 합니다.](use-roslyn-analyzers.md)
- [코드 분석 규칙 그룹화를 사용 하 여 규칙 집합](using-rule-sets-to-group-code-analysis-rules.md)