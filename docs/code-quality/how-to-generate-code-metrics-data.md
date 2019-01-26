---
title: IDE 또는 명령줄에서 코드의 메트릭 생성
ms.date: 11/02/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: f34f686b91d6a140e975c13eec72e8703a1b47ef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54945253"
---
# <a name="how-to-generate-code-metrics-data"></a>방법: 코드 메트릭 데이터 생성

하나 이상의 프로젝트 또는 전체 솔루션에 대해 코드 메트릭 결과 생성할 수 있습니다. 코드 메트릭 및 사용할 수 있는 Visual Studio 대화형 개발 환경 (IDE) 내에 C# 및 Visual Basic 프로젝트의 경우 명령줄에서.

또한 설치할 수 있습니다는 [NuGet 패키지](https://dotnet.myget.org/feed/roslyn-analyzers/package/nuget/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.2-beta2-63202-01) 포함 하는 네 가지 코드 메트릭 [분석기](roslyn-analyzers-overview.md) 규칙: CA1501, CA1502, CA1505, 및 CA1506 합니다. 이러한 규칙은 기본적으로 비활성화 되어 있지만 설정할 수 있습니다 **솔루션 탐색기** 또는 [규칙 집합](using-rule-sets-to-group-code-analysis-rules.md) 파일입니다.

## <a name="visual-studio-ide-code-metrics"></a>Visual Studio IDE 코드 메트릭

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

## <a name="command-line-code-metrics"></a>명령줄 코드 메트릭

명령줄에서 코드 메트릭 데이터를 생성할 수 있습니다 C# 및.NET Framework,.NET Core 및.NET Standard 앱에 대 한 Visual Basic 프로젝트입니다. 명령줄 코드 메트릭 도구 라고 *Metrics.exe*합니다.

가져오려고 합니다 *Metrics.exe* 실행을 수행 해야 합니다 [직접 생성할](#generate-the-executable)합니다. 가까운 미래에 [게시 된 버전의 *Metrics.exe* 사용할 수 있습니다](https://github.com/dotnet/roslyn-analyzers/issues/1756) 하므로 직접 빌드할 필요가 없습니다.

### <a name="generate-the-executable"></a>실행 파일을 생성 합니다.

실행 파일을 생성할 *Metrics.exe*, 다음이 단계를 수행 합니다.

1. 복제는 [dotnet/roslyn 분석기](https://github.com/dotnet/roslyn-analyzers) 리포지토리.
2. 관리자 권한으로 Visual Studio 용 개발자 명령 프롬프트를 엽니다.
3. 루트에서의 **roslyn 분석기** 리포지토리에서 다음 명령을 실행 합니다. `Restore.cmd`
4. 디렉터리를 변경 *src\Tools*합니다.
5. 빌드하려면 다음 명령을 실행 합니다 **Metrics.csproj** 프로젝트:

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   명명 된 실행 파일 *Metrics.exe* 에서 생성 되는 *artifacts\bin* 의 리 포 루트에서 디렉터리입니다.

   > [!TIP]
   > 빌드할 *Metrics.exe* 에서 [레거시 모드](#legacy-mode), 다음 명령을 실행 합니다.
   >
   > ```shell
   > msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
   > ```

### <a name="usage"></a>사용법

실행할 *Metrics.exe*인수로 솔루션 및 XML 출력 파일, 프로젝트를 제공 합니다. 예를 들어:

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

### <a name="output"></a>출력

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
                  <Method Name="void Program.Main(string[] args)" File="C:\Users\mavasani\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
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

### <a name="tool-differences"></a>도구 차이점

이전 버전의 Visual Studio, Visual Studio 2015를 포함 하 여 호출 하는 명령줄 코드 메트릭 도구 포함 *Metrics.exe*합니다. 이 이전 버전의 도구는 어셈블리 기반 분석, 이진 분석을 수행 했습니다. 새로운 도구는 대신 소스 코드를 분석합니다. 때문에 새 *Metrics.exe* 은 소스 코드를 기반으로 결과의 이전 버전에서 생성 한 내용을 다릅니다 *Metrics.exe* 및 Visual Studio 2017 ide.

새 *Metrics.exe* 도구 솔루션 및 프로젝트를 로드할 수 있다면 소스 코드 오류, 경우에 메트릭을 계산할 수 있습니다.

#### <a name="metric-value-differences"></a>메트릭 값 차이점

합니다 `LinesOfCode` 보다 정확 하 고 새 신뢰할 수 있는 메트릭은입니다 *Metrics.exe*합니다. Codegen 차이 무관 하 고 도구 집합을 런타임에 변경 될 때 변경 되지 않습니다. 새 *Metrics.exe* 실제 빈 줄 및 주석이 포함 하 여 코드 줄을 계산 합니다.

와 같은 다른 메트릭을 `CyclomaticComplexity` 및 `MaintainabilityIndex` 이전 버전의 동일한 수식을 사용 하 여 *Metrics.exe*, 하지만 새 *Metrics.exe* 개수를 `IOperations` (논리 지침을 원본) IL (중간 언어) 명령 대신 합니다. 이전 버전의 숫자 다소 달라 집니다 *Metrics.exe* 및 Visual Studio 2017 IDE 코드 메트릭 결과입니다.

### <a name="legacy-mode"></a>레거시 모드

빌드할 수도 있습니다 *Metrics.exe* 에 *레거시 모드*합니다. 레거시 모드 버전의 도구는 생성 된 도구의 이전 버전에 보다 가까이 메트릭 값을 생성 합니다. 레거시 모드에서는 또한 *Metrics.exe* 동일한 메서드 집합에는 이전 버전의 도구로 생성 된 코드 메트릭이 형식에 대 한 코드 메트릭을 생성 합니다. 예를 들어, 필드 및 속성 이니셜라이저에 대 한 코드 메트릭 데이터를 생성 하지 것입니다. 레거시 모드는 이전 버전과 호환성 또는 코드 체크 인 게이트 경우 메트릭을 기반으로 코드 번호에 대 한 유용 합니다. 빌드하는 명령 *Metrics.exe* 레거시 모드:

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

자세한 내용은 [레거시 모드에서 코드 메트릭을 생성 하는 사용](https://github.com/dotnet/roslyn-analyzers/pull/1841)합니다.

## <a name="see-also"></a>참고자료

- [코드 메트릭 결과 창 사용](../code-quality/working-with-code-metrics-data.md)
- [코드 메트릭 값](../code-quality/code-metrics-values.md)
