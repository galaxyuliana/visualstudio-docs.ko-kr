---
title: 코드 검사 분석 사용자 지정
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bb4b8625c69c28ca6d9a2e0a4b86122e810a87e4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935815"
---
# <a name="customize-code-coverage-analysis"></a>코드 검사 분석 사용자 지정

기본적으로 코드 검사는 단위 테스트 중에 로드되는 모든 솔루션 어셈블리를 분석합니다. 이 기본 동작은 대부분은 문제 없이 작동하므로 사용하는 것이 좋습니다. 자세한 내용은 [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)을 참조하세요.

코드 검사 결과에서 테스트 코드를 제외하고 애플리케이션 코드만 포함하려면 테스트 클래스에 <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> 특성을 추가합니다.

솔루션의 일부가 아닌 어셈블리를 포함하려면 이러한 어셈블리에 대한 *.pdb* 파일을 얻어서 어셈블리 *.dll* 파일과 동일한 폴더에 복사합니다.

## <a name="run-settings-file"></a>실행 설정 파일

[실행 설정 파일](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)은 유닛 테스트 도구에서 사용하는 구성 파일입니다. 고급 코드 검사 설정은 *.runsettings* 파일에서 지정합니다.

코드 검사를 사용자 지정하려면 다음 단계를 수행합니다.

1. 실행 설정 파일을 솔루션에 추가합니다. **솔루션 탐색기**의 솔루션 바로 가기 메뉴에서 **추가** > **새 항목**, **XML File**을 차례로 선택합니다. 파일을 *CodeCoverage.runsettings*와 같은 이름으로 저장합니다.

1. 이 문서의 끝 부분에 있는 예제 파일에서 콘텐츠를 추가한 다음, 다음 섹션에 설명된 대로 각자의 요구 사항에 맞게 사용자 지정합니다.

1. 실행 설정 파일을 선택하려면 **테스트** 메뉴에서 **테스트 설정** > **테스트 설정 파일 선택**을 선택합니다. 명령줄 또는 빌드 워크플로에서 테스트를 실행하기 위한 실행 설정 파일을 지정하려면 [ *.runsettings* 파일을 사용하여 단위 데스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md#specify-a-run-settings-file)을 참조하세요.

   **코드 검사 분석**을 선택하면 실행 설정 파일에서 구성 정보를 읽습니다.

   > [!TIP]
   > 테스트를 실행하거나 코드를 업데이트하면 이전 코드 검사 결과 및 코드 강조가 자동으로 숨겨지지 않습니다.

사용자 지정 설정을 해제했다 다시 사용하도록 설정하려면 **테스트** > **테스트 설정** 메뉴에서 파일을 선택 취소 또는 선택합니다.

![사용자 지정 설정 파일로 설정 메뉴 테스트](../test/media/codecoverage-settingsfile.png)

### <a name="specify-symbol-search-paths"></a>기호 검색 경로 지정

코드 검사에는 어셈블리에 대한 기호 파일(*.pdb* 파일)이 필요합니다. 솔루션에서 빌드한 어셈블리의 경우 기호 파일은 대개 이진 파일과 함께 있으며 코드 검사는 자동으로 실행됩니다. 하지만 코드 검사 분석에 참조된 어셈블리를 포함하려는 경우가 있습니다. 이런 경우에 *.pdb* 파일이 이진 파일과 가깝지 않을 수 있지만 *.runsettings* 파일에서 기호 검색 경로를 지정할 수 있습니다.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!NOTE]
> 기호 확인은 어셈블리가 많은 원격 파일 위치를 사용할 경우 특히 오래 걸릴 수 있습니다. 따라서 *.pdb* 파일을 이진(*.dll* 및.*exe*) 파일과 같은 로컬 위치에 복사하는 것이 좋습니다.

### <a name="exclude-and-include"></a>포함 및 제외

코드 검사 분석에서 지정한 어셈블리를 제외할 수 있습니다. 예:

```xml
<ModulePaths>
  <Exclude>
   <ModulePath>Fabrikam.Math.UnitTest.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Exclude>
</ModulePaths>
```

대신 포함할 어셈블리를 지정할 수 있습니다. 이 방법은 솔루션에 어셈블리를 추가할 경우 목록에 추가해야 하는 점을 기억해야 한다는 단점이 있습니다.

```xml
<ModulePaths>
  <Include>
   <ModulePath>Fabrikam.Math.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Include>
</ModulePaths>
```

**Include**가 비어 있을 경우, 코드 검사 처리에는 로드된 모든 어셈블리 및 *.pdb* 파일이 검색되는 모든 어셈블리가 포함됩니다. 코드 검사에는 **Exclude** 목록의 절과 일치하는 항목이 포함되지 않습니다.

**Include**는 **Exclude** 전에 처리됩니다.

### <a name="regular-expressions"></a>정규식

Include 및 exclude 노드는 정규식을 사용합니다. 자세한 내용은 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하세요. 정규식은 와일드카드와 다릅니다. 특히 다음과 같습니다.

- **.\\***는 모든 문자의 문자열과 일치합니다.

- **\\.** 점 “.”과 일치합니다.

- **\\(   \\)** 는 괄호 “(  )”와 일치합니다.

- **\\\\**파일 경로 구분 기호 “\\”와 일치합니다.

- **^** 는 문자열의 시작과 일치합니다.

- **$** 는 문자열의 끝과 일치합니다.

모든 일치 항목은 대소문자를 구분하지 않습니다.

예:

```xml
<ModulePaths>
  <Include>
    <!-- Include all loaded .dll assemblies (but not .exe assemblies): -->
    <ModulePath>.*\.dll$</ModulePath>
  </Include>
  <Exclude>
    <!-- But exclude some assemblies: -->
    <ModulePath>.*\\Fabrikam\.MyTests1\.dll$</ModulePath>
    <!-- Exclude all file paths that contain "Temp": -->
    <ModulePath>.*Temp.*</ModulePath>
  </Exclude>
</ModulePaths>
```

> [!WARNING]
> 이스케이프되지 않은 괄호 또는 일치하지 않는 괄호와 같이 정규식에 오류가 있는 경우 코드 검사 분석이 실행되지 않습니다.

### <a name="other-ways-to-include-or-exclude-elements"></a>요소를 포함 또는 제외하는 다른 방법

- **ModulePath** - 어셈블리 파일 경로로 지정한 어셈블리와 일치시킵니다.

- **CompanyName** – 어셈블리를 **회사** 특성으로 일치시킵니다.

- **PublicKeyToken** – 서명된 어셈블리를 공개 키 토큰으로 일치시킵니다.

- **소스** – 요소를 소스 파일이 정의된 경로 이름으로 일치시킵니다.

- **특성** – 특정 특성이 연결된 요소에 일치시킵니다. 특성의 전체 이름을 지정하고 이름 끝의 "특성"을 포함합니다.

- **함수** – 절차, 함수 또는 메서드를 정규화된 이름으로 일치시킵니다. 함수 이름을 일치시키려면 정규식은 네임스페이스, 클래스 이름, 메서드 이름, 매개 변수 목록을 포함한 함수의 정규화된 이름과 일치해야 합니다. 예:

   ```csharp
   Fabrikam.Math.LocalMath.SquareRoot(double);
   ```

   ```cpp
   Fabrikam::Math::LocalMath::SquareRoot(double)
   ```

   ```xml
   <Functions>
     <Include>
       <!-- Include methods in the Fabrikam namespace: -->
       <Function>^Fabrikam\..*</Function>
       <!-- Include all methods named EqualTo: -->
       <Function>.*\.EqualTo\(.*</Function>
     </Include>
     <Exclude>
       <!-- Exclude methods in a class or namespace named UnitTest: -->
       <Function>.*\.UnitTest\..*</Function>
     </Exclude>
   </Functions>
   ```

## <a name="sample-runsettings-file"></a>샘플 .runsettings 파일

이 코드를 복사하고 필요에 따라 편집합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- File name extension must be .runsettings -->
<RunSettings>
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">
        <Configuration>
          <CodeCoverage>
<!--
Additional paths to search for .pdb (symbol) files. Symbols must be found for modules to be instrumented.
If .pdb files are in the same folder as the .dll or .exe files, they are automatically found. Otherwise, specify them here.
Note that searching for symbols increases code coverage runtime. So keep this small and local.
-->
<!--
            <SymbolSearchPaths>
                   <Path>C:\Users\User\Documents\Visual Studio 2012\Projects\ProjectX\bin\Debug</Path>
                   <Path>\\mybuildshare\builds\ProjectX</Path>
            </SymbolSearchPaths>
-->

<!--
About include/exclude lists:
Empty "Include" clauses imply all; empty "Exclude" clauses imply none.
Each element in the list is a regular expression (ECMAScript syntax). See https://docs.microsoft.com/visualstudio/ide/using-regular-expressions-in-visual-studio.
An item must first match at least one entry in the include list to be included.
Included items must then not match any entries in the exclude list to remain included.
-->

            <!-- Match assembly file paths: -->
            <ModulePaths>
              <Include>
                <ModulePath>.*\.dll$</ModulePath>
                <ModulePath>.*\.exe$</ModulePath>
              </Include>
              <Exclude>
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
              </Exclude>
            </ModulePaths>

            <!-- Match fully qualified names of functions: -->
            <!-- (Use "\." to delimit namespaces in C# or Visual Basic, "::" in C++.)  -->
            <Functions>
              <Exclude>
                <Function>^Fabrikam\.UnitTest\..*</Function>
                <Function>^std::.*</Function>
                <Function>^ATL::.*</Function>
                <Function>.*::__GetTestMethodInfo.*</Function>
                <Function>^Microsoft::VisualStudio::CppCodeCoverageFramework::.*</Function>
                <Function>^Microsoft::VisualStudio::CppUnitTestFramework::.*</Function>
              </Exclude>
            </Functions>

            <!-- Match attributes on any code element: -->
            <Attributes>
              <Exclude>
                <!-- Don't forget "Attribute" at the end of the name -->
                <Attribute>^System\.Diagnostics\.DebuggerHiddenAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.DebuggerNonUserCodeAttribute$</Attribute>
                <Attribute>^System\.Runtime\.CompilerServices.CompilerGeneratedAttribute$</Attribute>
                <Attribute>^System\.CodeDom\.Compiler.GeneratedCodeAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.CodeAnalysis.ExcludeFromCodeCoverageAttribute$</Attribute>
              </Exclude>
            </Attributes>

            <!-- Match the path of the source files in which each method is defined: -->
            <Sources>
              <Exclude>
                <Source>.*\\atlmfc\\.*</Source>
                <Source>.*\\vctools\\.*</Source>
                <Source>.*\\public\\sdk\\.*</Source>
                <Source>.*\\microsoft sdks\\.*</Source>
                <Source>.*\\vc\\include\\.*</Source>
              </Exclude>
            </Sources>

            <!-- Match the company name property in the assembly: -->
            <CompanyNames>
              <Exclude>
                <CompanyName>.*microsoft.*</CompanyName>
              </Exclude>
            </CompanyNames>

            <!-- Match the public key token of a signed assembly: -->
            <PublicKeyTokens>
              <!-- Exclude Visual Studio extensions: -->
              <Exclude>
                <PublicKeyToken>^B77A5C561934E089$</PublicKeyToken>
                <PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>
                <PublicKeyToken>^31BF3856AD364E35$</PublicKeyToken>
                <PublicKeyToken>^89845DCD8080CC91$</PublicKeyToken>
                <PublicKeyToken>^71E9BCE111E9429C$</PublicKeyToken>
                <PublicKeyToken>^8F50407C4E9E73B6$</PublicKeyToken>
                <PublicKeyToken>^E361AF139669C375$</PublicKeyToken>
              </Exclude>
            </PublicKeyTokens>

            <!-- We recommend you do not change the following values: -->
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
            <CollectFromChildProcesses>True</CollectFromChildProcesses>
            <CollectAspDotNet>False</CollectAspDotNet>

          </CodeCoverage>
        </Configuration>
      </DataCollector>
    </DataCollectors>
  </DataCollectionRunSettings>
</RunSettings>
```

## <a name="see-also"></a>참고 항목

- [실행 설정 파일을 사용하여 단위 테스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)
- [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [코드 단위 테스트](../test/unit-test-your-code.md)