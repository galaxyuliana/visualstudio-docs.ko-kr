---
title: IDE 또는 명령줄에서 코드의 메트릭 생성
ms.date: 11/02/2018
ms.topic: conceptual
helpviewer_keywords:
- code metrics data
- code metrics results
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4275e92b21289c5cf1e3243b2bc782a9e0821fde
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232751"
---
# <a name="how-to-generate-code-metrics-data"></a>방법: 코드 메트릭 데이터 생성

세 가지 방법으로 코드 메트릭 데이터를 생성할 수 있습니다.

- 설치 하 여 [FxCop 분석기](#fxcop-analyzers-code-metrics-rules) 고 포함 된 4 개의 코드 (유지 관리) 메트릭 규칙을 사용 하도록 설정 합니다.

- 선택 하 여 합니다 [ **분석** > **코드 메트릭 계산** ](#calculate-code-metrics-menu-command) Visual Studio 내에서 메뉴 명령입니다.

- [명령줄](#command-line-code-metrics) 에 대 한 C# 및 Visual Basic 프로젝트입니다.

## <a name="fxcop-analyzers-code-metrics-rules"></a>FxCop 분석기 코드 메트릭 규칙

합니다 [FxCopAnalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) 코드는 몇 가지 메트릭을 포함 [분석기](roslyn-analyzers-overview.md) 규칙:

- [CA1501](ca1501-avoid-excessive-inheritance.md)
- [CA1502](ca1502-avoid-excessive-complexity.md)
- [CA1505](ca1505-avoid-unmaintainable-code.md)
- [CA1506](ca1506-avoid-excessive-class-coupling.md)

이러한 규칙은 기본적으로 비활성화 되어 있지만 설정할 수 있습니다 [ **솔루션 탐색기** ](use-roslyn-analyzers.md#set-rule-severity-from-solution-explorer) 또는 [규칙 집합](using-rule-sets-to-group-code-analysis-rules.md) 파일입니다. 예를 들어.ruleset 파일 경고로 CA1502 규칙을 사용 하려면 다음 항목이 포함 됩니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="Rules" Description="Rules" ToolsVersion="16.0">
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1502" Action="Warning" />
  </Rules>
</RuleSet>
```

### <a name="configuration"></a>구성

코드 메트릭을 규칙 FxCop 분석기에서 패키지 실행 임계값을 구성할 수 있습니다.

1. 텍스트 파일을 만듭니다. 예를 들어 이름을 지정할 수 있습니다 *CodeMetricsConfig.txt*합니다.

2. 다음 형식으로 텍스트 파일에 원하는 임계값을 추가 합니다.

   ```txt
   CA1502: 10
   ```

   이 예제에서는 규칙 [CA1502](ca1502-avoid-excessive-complexity.md) 메서드의 순환 복잡성이 10 보다 큰 경우에 발생 하도록 구성 됩니다.

3. 에 **속성** 프로젝트 파일 또는 Visual Studio의 창 표시 된 구성 파일의 빌드 동작 [ **AdditionalFiles**](../ide/build-actions.md#build-action-values)합니다. 예를 들어:

   ```xml
   <ItemGroup>
     <AdditionalFiles Include="CodeMetricsConfig.txt" />
   </ItemGroup>
   ```

## <a name="calculate-code-metrics-menu-command"></a>메뉴 명령 코드 메트릭 계산

사용 하 여 IDE에서 열린 프로젝트 중 하나 또는 모두에 대해 코드 메트릭을 생성 합니다 **분석** > **코드 메트릭 계산** 메뉴.

### <a name="generate-code-metrics-results-for-an-entire-solution"></a>전체 솔루션에 대해 코드 메트릭 결과 생성

다음 방법 중 하나에서 전체 솔루션에 대해 코드 메트릭 결과 생성할 수 있습니다.

- 메뉴 모음에서 선택 **분석** > **코드 메트릭 계산** > **솔루션용**합니다.

- **솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택한 **코드 메트릭 계산**합니다.

- 에 **코드 메트릭 결과** 창에서 선택 합니다 **솔루션에 대해 코드 메트릭 계산** 단추.

결과가 생성 되 고 **코드 메트릭 결과** 창이 표시 됩니다. 결과 세부 정보를 보려면에서 트리를 확장 합니다 **계층** 열입니다.

### <a name="generate-code-metrics-results-for-one-or-more-projects"></a>하나 이상의 프로젝트에 대해 코드 메트릭 결과 생성

1. **솔루션 탐색기**, 하나 이상의 프로젝트를 선택 합니다.

1. 메뉴 모음에서 선택 **분석** > **코드 메트릭 계산** > **선택한 프로젝트에 대 한**합니다.

결과가 생성 되 고 **코드 메트릭 결과** 창이 표시 됩니다. 결과 세부 정보를 보려면에서 트리를 확장 합니다 **계층**합니다.

::: moniker range="vs-2017"

> [!NOTE]
> 합니다 **코드 메트릭 계산** 명령은.NET Core 및.NET Standard 프로젝트에 대 한 작동 하지 않습니다. .NET Core 또는.NET Standard 프로젝트에 대해 코드 메트릭을 계산 하려면 다음을 수행할 수 있습니다.
>
> - 코드 메트릭을 계산 합니다 [명령줄](#command-line-code-metrics) 대신
>
> - 로 업그레이드 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

::: moniker-end

## <a name="command-line-code-metrics"></a>명령줄 코드 메트릭

명령줄에서 코드 메트릭 데이터를 생성할 수 있습니다 C# 및.NET Framework,.NET Core 및.NET Standard 앱에 대 한 Visual Basic 프로젝트입니다. 코드 메트릭 명령줄에서를 실행 하려면 설치 합니다 [Microsoft.CodeAnalysis.Metrics NuGet 패키지](#microsoftcodeanalysismetrics-nuget-package) 빌드하거나 합니다 [Metrics.exe](#metricsexe) 실행 직접.

### <a name="microsoftcodeanalysismetrics-nuget-package"></a>Microsoft.CodeAnalysis.Metrics NuGet 패키지

설치 하는 가장 쉬운 방법은 명령줄에서 코드 메트릭 데이터를 생성 하는 것은 [Microsoft.CodeAnalysis.Metrics](https://www.nuget.org/packages/Microsoft.CodeAnalysis.Metrics/) NuGet 패키지. 패키지를 설치한 후 실행 `msbuild /t:Metrics` 프로젝트 파일이 포함 된 디렉터리에서. 예를 들어:

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:29:57 PM.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics\Metrics.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:ClassLibrary3.Metrics.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'ClassLibrary3.Metrics.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

출력 파일 이름을 지정 하 여 재정의할 수 있습니다 `/p:MetricsOutputFile=<filename>`합니다. 가져올 수도 있습니다 [레거시 스타일](#previous-versions) 지정 하 여 메트릭 데이터를 코드 `/p:LEGACY_CODE_METRICS_MODE=true`합니다. 예를 들어:

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics /p:LEGACY_CODE_METRICS_MODE=true /p:MetricsOutputFile="Legacy.xml"
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:31:00 PM.
The "MetricsOutputFile" property is a global property, and cannot be modified.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics.Legacy\Metrics.Legacy.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:Legacy.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'Legacy.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

### <a name="code-metrics-output"></a>코드 메트릭 출력

생성된 된 XML 출력에는 다음 형식을 갖습니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeMetricsReport Version="1.0">
  <Targets>
    <Target Name="ConsoleApp20.csproj">
      <Assembly Name="ConsoleApp20, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null">
        <Metrics>
          <Metric Name="MaintainabilityIndex" Value="100" />
          <Metric Name="CyclomaticComplexity" Value="1" />
          <Metric Name="ClassCoupling" Value="1" />
          <Metric Name="DepthOfInheritance" Value="1" />
          <Metric Name="LinesOfCode" Value="11" />
        </Metrics>
        <Namespaces>
          <Namespace Name="ConsoleApp20">
            <Metrics>
              <Metric Name="MaintainabilityIndex" Value="100" />
              <Metric Name="CyclomaticComplexity" Value="1" />
              <Metric Name="ClassCoupling" Value="1" />
              <Metric Name="DepthOfInheritance" Value="1" />
              <Metric Name="LinesOfCode" Value="11" />
            </Metrics>
            <Types>
              <NamedType Name="Program">
                <Metrics>
                  <Metric Name="MaintainabilityIndex" Value="100" />
                  <Metric Name="CyclomaticComplexity" Value="1" />
                  <Metric Name="ClassCoupling" Value="1" />
                  <Metric Name="DepthOfInheritance" Value="1" />
                  <Metric Name="LinesOfCode" Value="7" />
                </Metrics>
                <Members>
                  <Method Name="void Program.Main(string[] args)" File="C:\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
                    <Metrics>
                      <Metric Name="MaintainabilityIndex" Value="100" />
                      <Metric Name="CyclomaticComplexity" Value="1" />
                      <Metric Name="ClassCoupling" Value="1" />
                      <Metric Name="LinesOfCode" Value="4" />
                    </Metrics>
                  </Method>
                </Members>
              </NamedType>
            </Types>
          </Namespace>
        </Namespaces>
      </Assembly>
    </Target>
  </Targets>
</CodeMetricsReport>
```

### <a name="metricsexe"></a>Metrics.exe

NuGet 패키지를 설치 하지 않으려는 경우 생성 하 고 사용 하 여 수를 *Metrics.exe* 직접 실행 합니다. 생성 하는 *Metrics.exe* 실행:

1. 복제는 [dotnet/roslyn 분석기](https://github.com/dotnet/roslyn-analyzers) 리포지토리.
2. 관리자 권한으로 Visual Studio 용 개발자 명령 프롬프트를 엽니다.
3. 루트에서의 **roslyn 분석기** 리포지토리에서 다음 명령을 실행 합니다. `Restore.cmd`
4. 디렉터리를 변경 *src\Tools*합니다.
5. 빌드하려면 다음 명령을 실행 합니다 **Metrics.csproj** 프로젝트:

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   명명 된 실행 파일 *Metrics.exe* 에서 생성 되는 *artifacts\bin* 의 리 포 루트에서 디렉터리입니다.

#### <a name="metricsexe-usage"></a>Metrics.exe 사용

실행할 *Metrics.exe*인수로 솔루션 및 XML 출력 파일, 프로젝트를 제공 합니다. 예를 들어:

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

#### <a name="legacy-mode"></a>레거시 모드

빌드를 선택할 수 있습니다 *Metrics.exe* 에 *레거시 모드*합니다. 도구의 레거시 모드 버전 무엇에 보다 가까이 메트릭 값을 생성 [이전 버전의 도구로 생성 된](#previous-versions)합니다. 레거시 모드에서는 또한 *Metrics.exe* 동일한 메서드 집합에는 이전 버전의 도구로 생성 된 코드 메트릭이 형식에 대 한 코드 메트릭을 생성 합니다. 예를 들어, 필드 및 속성 이니셜라이저에 대 한 코드 메트릭 데이터를 생성 하지 것입니다. 레거시 모드는 이전 버전과 호환성 또는 코드 체크 인 게이트 경우 메트릭을 기반으로 코드 번호에 대 한 유용 합니다. 빌드하는 명령 *Metrics.exe* 레거시 모드:

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

자세한 내용은 [레거시 모드에서 코드 메트릭을 생성 하는 사용](https://github.com/dotnet/roslyn-analyzers/pull/1841)합니다.

### <a name="previous-versions"></a>이전 버전

Visual Studio 2015도 호출 된 명령줄 코드 메트릭 도구 포함 *Metrics.exe*합니다. 이 이전 버전의 도구는 어셈블리 기반 분석, 이진 분석을 수행 했습니다. 새 *Metrics.exe* 도구 대신 소스 코드를 분석 합니다. 때문에 새 *Metrics.exe* 도구는 이전 버전의 Visual Studio IDE에 의해 생성 된 결과 소스 코드 기반, 명령줄 코드 메트릭을 *Metrics.exe*합니다.

새 명령줄 코드 메트릭 도구 솔루션 및 프로젝트를 로드할 수 있다면 소스 코드 오류, 경우에 메트릭을 계산 합니다.

#### <a name="metric-value-differences"></a>메트릭 값 차이점

`LinesOfCode` 더 정확 하 고 새 명령줄 코드 메트릭 도구에서 신뢰할 수 있는 메트릭은입니다. Codegen 차이 무관 하 고 도구 집합을 런타임에 변경 될 때 변경 되지 않습니다. 새 도구 실제 빈 줄 및 주석이 포함 하 여 코드 줄을 계산 합니다.

와 같은 다른 메트릭을 `CyclomaticComplexity` 및 `MaintainabilityIndex` 이전 버전의 동일한 수식을 사용 하 여 *Metrics.exe*, 새로운 도구 수를 계산 하지만 `IOperations` (논리적 원본이 지침) 대신 중간 언어 (IL) 지침입니다. 이전 버전의 Visual Studio IDE에 의해 생성 된 번호를 다소 달라 집니다 *Metrics.exe*합니다.

## <a name="see-also"></a>참고자료

- [코드 메트릭 결과 창 사용](../code-quality/working-with-code-metrics-data.md)
- [코드 메트릭 값](../code-quality/code-metrics-values.md)
