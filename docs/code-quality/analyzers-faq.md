---
title: EditorConfig 분석기 비교
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bec9296f15c48cf3b327c78cd0ce7d57adafa002
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874685"
---
# <a name="analyzers-faq"></a>분석기 FAQ

이 페이지에서는 Visual Studio에서 Roslyn 분석기에 대 한 일부 자주 묻는 질문에 대답 합니다.

## <a name="roslyn-analyzers-versus-editorconfig"></a>Roslyn 분석기.editorconfig 비교

**Q**: Roslyn 분석기 또는.editorconfig 코드 스타일에 대 한 사용 해야 합니까?

**A**: Roslyn 분석기 및.editorconfig 파일에 직접에서 직접 작동합니다. 코드 스타일을 정의 하는 경우 [.editorconfig 파일에](../ide/editorconfig-code-style-settings-reference.md) 또는 합니다 [텍스트 편집기 옵션](../ide/code-styles-and-quick-actions.md) 페이지를 구성 하는 실제로 Visual Studio에 기본 제공 되는 Roslyn 분석기입니다. EditorConfig 파일 같은 몇 가지 타사 분석기 패키지를 구성 하려면 사용할 수도 있습니다 [FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig 규칙 집합 비교

**Q**: 규칙 집합 또는.editorconfig 파일을 사용 하 여 내 분석기를 구성 해야 합니까?

**A**: 규칙 집합.editorconfig 파일와 분석기를 구성 하는 상호 배타적인 방법입니다. 공존할 수 있습니다. [규칙 집합](analyzer-rule-sets.md) 사용 하면 사용 하도록 설정 및 규칙을 사용 하지 않도록 설정 하 고 심각도 설정 합니다. EditorConfig 파일에는 규칙을 구성 하는 다른 방법을 제공 합니다. FxCop 분석기에 대 한.editorconfig 파일 수 [분석 하는 코드의 유형을 정의](fxcop-analyzer-options.md)합니다. Visual Studio에 기본 제공 되는 분석기에 대 한.editorconfig 파일 수 [기본 코드 스타일을 정의](../ide/editorconfig-code-style-settings-reference.md) 코드 베이스에 대 한 합니다.

일부 타사 분석기로 표시 된 텍스트 파일을 사용 하 여 구성 된 규칙 집합과.editorconfig 파일을 실행 하는 것 외에도 [추가 파일](../ide/build-actions.md#build-action-values) 에 C# 및 VB 컴파일러입니다.

> [!NOTE]
> 규칙 집합 수 있지만 정적 코드 분석 규칙 구성에 EditorConfig 파일을 사용할 수 없습니다.

## <a name="analyzers-in-ci-builds"></a>CI 빌드의 분석기

**Q**: CI (지속적인 통합) 빌드에 분석기가 작동 하나요?

**A**: 예. 이러한 규칙은 NuGet 패키지에서 설치 되는 분석기에 대 한 [빌드 시간에 적용](roslyn-analyzers-overview.md#build-errors)CI 빌드 중 등입니다. 둘 다에서 CI 빌드 관련 규칙 구성에 사용 되는 분석기 [규칙 집합](analyzer-rule-sets.md) 하 고 [.editorconfig 파일](configure-fxcop-analyzers.md)합니다. 현재 Visual Studio에 기본 제공 되는 코드 분석기를 NuGet 패키지로 사용할 수 없는 및 이러한 규칙에서 CI 빌드를 시행 되지 않아.

## <a name="ide-analyzers-versus-stylecop"></a>StyleCop 및 IDE 분석기

**Q**: Visual Studio IDE 코드 분석기 및 StyleCop 분석기 간의 차이 무엇입니까?

**A**: Visual Studio IDE에서 코드 스타일 및 품질 문제를 모두 검색 하는 기본 제공 분석기를 포함 합니다. 이러한 규칙 도움이 도입 하 고 코드의 용이해 지 며 새로운 언어 기능을 사용 합니다. IDE 분석기는 지속적으로 업데이트 하는 각 Visual Studio 릴리스를 사용 하 여 합니다.

[StyleCop 분석기](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) 는 코드에서 스타일 일관성 확인 하는 제 3 자 분석기는 NuGet 패키지로 설치 합니다. 일반적으로 StyleCop 규칙 다른 하나의 스타일을 권장 하지 않고 코드에 대 한 개인 기본 설정을 기본 설정할 수 있습니다.

## <a name="analyzers-versus-static-code-analysis"></a>정적 코드 분석 및 분석기

**Q**: 분석기 및 정적 코드 분석의 차이 무엇입니까?

**A**: 정적 코드 분석 빌드가 완료 된 후 이진 파일을 분석 하는 반면 실시간에서 및 컴파일하는 동안 소스 코드를 분석 하는 분석기입니다. 자세한 내용은 [정적 코드 분석 및 Roslyn 분석기](roslyn-analyzers-overview.md#roslyn-analyzers-vs-static-code-analysis) 하 고 [FxCop 분석기 FAQ](fxcop-analyzers-faq.md)합니다.

## <a name="see-also"></a>참고자료

- [분석기 개요](roslyn-analyzers-overview.md)
- [EditorConfig에 대한 .NET 코딩 규칙 설정](../ide/editorconfig-code-style-settings-reference.md)