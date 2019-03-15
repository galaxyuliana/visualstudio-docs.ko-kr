---
title: Editorconfig를 사용 하 여 FxCop 분석기를 구성 합니다.
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ac751b7ec130b6bfbb18752c02b491b6c342f172
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874701"
---
# <a name="configure-fxcop-analyzers"></a>FxCop 분석기를 구성 합니다.

합니다 [FxCop 분석기](install-fxcop-analyzers.md) Roslyn 분석기로 변환 되는 정적 코드 분석에서 가장 중요 한 "FxCop" 규칙으로 구성 됩니다. 두 가지 방법으로 FxCop 코드 분석기를 구성할 수 있습니다.

- 사용 하 여는 [규칙 집합](#fxcop-analyzer-rule-sets), 또는 규칙을 사용 하지 않도록 설정 하 고 개별 규칙 위반에 대 한 심각도 설정할 수 있습니다.

- 2.6.3 버전부터 합니다 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet 패키지를 통해를 [.editorconfig 파일](#editorconfig-file)합니다. 합니다 [구성 가능한 옵션](fxcop-analyzer-options.md) 부분을 구체화할 수에 코드 베이스를 분석 합니다.

> [!TIP]
> FxCop 정적 코드 분석 및 FxCop 분석기의 차이점에 대 한 자세한 내용은 [FxCop 분석기 FAQ](fxcop-analyzers-faq.md)합니다.

## <a name="fxcop-analyzer-rule-sets"></a>FxCop 분석기 규칙 집합

FxCop 분석기를 구성 하는 한 가지 방법은 XML를 사용 하는 것 *규칙 집합*합니다. 규칙 집합은 특정 조건과 대상된 문제를 식별 하는 코드 분석 규칙 그룹화 합니다. 규칙 집합을 사용 하 여 또는 규칙을 사용 하지 않도록 설정 하 고 개별 규칙 위반에 대 한 심각도 설정할 수 있습니다.

FxCop 분석기 NuGet 패키지에는 다음 규칙 범주에 대 한 미리 정의 된 규칙 집합에 포함 됩니다.

- 디자인
- 문서
- 유지 관리
- 명명
- 성능
- 안정성
- 보안
- 사용법

자세한 내용은 [Roslyn 분석기에 대 한 규칙 집합](analyzer-rule-sets.md)합니다.

## <a name="editorconfig-file"></a>EditorConfig 파일

키-값 쌍을 추가 하 여 분석기 규칙을 구성할 수 있습니다는 [.editorconfig](https://editorconfig.org) 파일입니다. 구성 파일 [프로젝트에 특정](#per-project-configuration) 될 수도 있습니다 [공유](#shared-configuration) 두 개 이상의 프로젝트 사이입니다.

### <a name="per-project-configuration"></a>프로젝트 구성

특정 프로젝트에 대 한 분석기.editorconfig 기반 구성을 사용 하도록 하려면 추가 *.editorconfig* 파일을 프로젝트의 루트 디렉터리입니다.

> [!TIP]
> 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 프로젝트에.editorconfig 파일을 추가할 수 있습니다 **솔루션 탐색기** 를 선택 하 고 **추가** > **새 항목**합니다. 에 **새 항목 추가** 창에서 입력 **editorconfig** 검색 상자에 있습니다. 선택 합니다 **editorconfig 파일 (기본값)** 템플릿을 선택 하 고 **추가**합니다.
>
> ![Visual Studio에서 프로젝트에 editorconfig 항목 추가](media/add-editorconfig-file.png)

현재 지원 되지 않습니다 계층적 "결합".editorconfig 파일에 대 한 다른 디렉터리 수준에서 예를 들어, 솔루션 및 프로젝트 수준에 존재 합니다.

### <a name="shared-configuration"></a>공유 구성

두 개 이상의 프로젝트 간에 분석기 구성에 대 한.editorconfig 파일을 공유할 수 있지만 몇 가지 추가 단계가 필요 합니다.

1. 저장 된 *.editorconfig* 공통 위치로 파일입니다.

2. 만들기는 *.props* 다음과 같은 콘텐츠로 파일:

   ```xml
   <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <PropertyGroup>
       <SkipDefaultEditorConfigAsAdditionalFile>true</SkipDefaultEditorConfigAsAdditionalFile>
     </PropertyGroup>
     <ItemGroup Condition="Exists('<your path>\.editorconfig')" >
       <AdditionalFiles Include="<your path>\.editorconfig" />
     </ItemGroup>
   </Project>
   ```

3. 행을 추가 하에 *.csproj* 또는 *.vbproj* 가져올 파일을 *.props* 이전 단계에서 만든 파일입니다. 가져올 FxCop 분석기는 모든 줄 전에이 줄을 배치 해야 합니다 *.props* 파일입니다. 예를 들어.props 파일 이름이 *editorconfig.props*:

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. 프로젝트를 다시 로드 합니다.

> [!NOTE]
> .Editorconfig 파일을 사용 하 여 레거시 FxCop 규칙 (정적 코드 분석 FxCop)을 구성할 수 없습니다.

## <a name="option-scopes"></a>옵션 범위

모든 규칙에 대해, 예를 들어, 명명, 디자인 규칙의 범주에 대해 또는 특정 규칙에 대 한 각 옵션을 구성할 수 있습니다.

### <a name="all-rules"></a>모든 규칙

모든 규칙에 대 한 옵션을 구성 하기 위한 구문은 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>규칙 범주

에 대 한 옵션을 구성 하기 위한 구문은 *범주* 규칙 (예: 이름 지정, 디자인 또는 성능)는 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality.RuleCategory.OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>특정 규칙

특정 규칙에 대 한 옵션을 구성 하기 위한 구문은 다음과 같습니다.

|구문|예제|
|-|-|
| dotnet_code_quality.RuleId.OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>참고자료

- [분석기 구성](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [FxCop 분석기](install-fxcop-analyzers.md)
