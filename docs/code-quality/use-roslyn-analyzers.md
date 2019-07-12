---
title: 분석기 규칙 심각도 및 제거
ms.date: 03/26/2019
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d4b5ad6ca824e6c7091c6c508b51c2d51501b2fd
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67821524"
---
# <a name="use-roslyn-analyzers"></a>Roslyn 분석기를 사용 합니다.

.NET 컴파일러 플랫폼 ("Roslyn") 분석기 규칙 또는 *진단*를 입력할 때 C# 또는 Visual Basic 코드를 분석 합니다. 각 진단의 프로젝트에 대 한 덮어쓸 수 있는 기본 심각도 및 표시 안 함 상태입니다. 이 문서에서는 규칙 집합을 사용 하 고 위반 표시 안 함 설정 규칙 심각도 설명 합니다.

## <a name="analyzers-in-solution-explorer"></a>솔루션 탐색기의 분석기

대부분의 사용자 지정 분석기 진단에서 수행할 수 있습니다 **솔루션 탐색기**합니다. 경우 있습니다 [분석기 설치](../code-quality/install-roslyn-analyzers.md) NuGet 패키지로 **분석기** 노드 아래에 나타납니다 합니다 **참조** 또는 **종속성** 에서노드 **솔루션 탐색기**합니다. 확장 하는 경우 **분석기**, 분석기 어셈블리 중 하나를 확장 하 고, 어셈블리의 모든 진단 정보를 표시 합니다.

![솔루션 탐색기에서 노드 분석기](media/analyzers-expanded-in-solution-explorer.png)

에 해당 설명 및 기본 심각도 포함 하는 진단의 속성을 볼 수는 **속성** 창입니다. 속성을 보려면 마우스 오른쪽 단추로 클릭 한 규칙과 선택 **속성**, 또는 규칙을 선택 하 고 누릅니다 **Alt**+**Enter**합니다.

![속성 창에서 진단 속성](media/analyzer-diagnostic-properties.png)

진단에 대 한 온라인 설명서를 보려면 진단을 마우스 오른쪽 단추로 클릭 하 고 선택 **도움말 보기**합니다.

각 진단의 옆에 있는 아이콘 **솔루션 탐색기** 규칙 집합 편집기에서 열면에 표시 되는 아이콘에 해당 합니다.

- 원 안에 "i" 나타냅니다는 [심각도](#rule-severity) 의 **정보**
- "!" 삼각형 나타냅니다는 [심각도](#rule-severity) 의 **경고**
- 원에 있는 "x" 표시를 [심각도](#rule-severity) 의 **오류**
- 밝은 색 배경의 원 안에 "i" 나타냅니다는 [심각도](#rule-severity) 의 **숨김**
- 원 안에 아래쪽 화살표를 사용 하는 진단 표시 되지 않습니다 나타냅니다.

![솔루션 탐색기에서 진단 아이콘](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>규칙 집합

A [규칙 집합](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) 은 개별 진단에 대 한 심각도 및 표시 안 함 상태를 저장 하는 XML 파일입니다.

> [!NOTE]
> 규칙 집합 (이진) 정적 코드 분석 및 Roslyn 분석기에서 규칙을 포함할 수 있습니다.

활성 규칙 규칙 집합 편집기에서 집합을 편집 하려면 마우스 오른쪽 단추로 클릭 합니다 **참조** > **분석기** 노드에서 **솔루션 탐색기** 를선택하고**활성 규칙 집합 열기**합니다. Visual Studio 파일 설정 기본 규칙의 복사본을 만들고, 이름을 처음 규칙 집합을 편집 하는 경우  *\<projectname >.ruleset*, 프로젝트에 추가 합니다. 이 사용자 지정 규칙 집합 active 규칙 프로젝트에 대 한 설정 됩니다.

활성 규칙 집합 프로젝트를 변경 하려면로 이동 합니다 **코드 분석** 프로젝트의 속성 탭 합니다. 규칙 집합 목록에서 선택 **이 규칙 집합 실행**합니다. 규칙 집합을 열려면 **엽니다**합니다.

> [!NOTE]
> .NET core 및.NET Standard 프로젝트 규칙 집합에 대 한 메뉴 명령을 지원 하지 않습니다 **솔루션 탐색기**, 예를 들어 **활성 규칙 집합 열기**합니다. .NET Core 또는.NET Standard 프로젝트에 대해 수동으로 설정 하는 기본이 아닌 규칙 지정 [추가 합니다 **CodeAnalysisRuleSet** 속성](using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project) 프로젝트 파일에 있습니다. Visual Studio에서 설정 하는 규칙 규칙 집합 편집기 UI 내에서 규칙을 구성할 수 있습니다.

## <a name="rule-severity"></a>규칙 심각도

분석기 규칙의 심각도 구성할 수 있습니다 또는 *진단을*이면 있습니다 [분석기 설치](../code-quality/install-roslyn-analyzers.md) NuGet 패키지로 합니다. 다음 표에서 진단에 대 한 심각도 옵션을 보여 줍니다.

|Severity|빌드 시 동작|편집기 동작|
|-|-|-|
|Error|위반으로 표시 *오류* 에 **오류 목록** 명령줄에서 빌드 출력 및 빌드 실패를 발생 합니다.|코드를 잘못 된 물결 및 스크롤 막대의 작은 빨간색 상자에 표시 된 빨간색 밑줄이 그어져 합니다.|
|경고|위반으로 표시 *경고* 에 **오류 목록** 명령줄에서 빌드 출력을 하며 빌드 실패를 발생 하지 않습니다.|녹색 물결 및 스크롤 막대의 작은 녹색 상자에 표시 된 밑줄이 그어져 코드를 위반 합니다.|
|정보|위반으로 표시 *메시지* 에 **오류 목록**, 및 명령줄 빌드 출력에 전혀 그렇지 않습니다.|물결 및 스크롤 막대의 작은 회색 상자에 표시 된 회색으로 밑줄이 그어져 코드를 위반 합니다.|
|숨김|비-사용자에 게 표시 합니다.|비-사용자에 게 표시 합니다. 하지만 진단 IDE 진단 엔진에 보고 됩니다.|
|없음|완전히 표시 되지 않습니다.|완전히 표시 되지 않습니다.|

또한 "다시 설정할 수 있습니다" 규칙의 심각도를 설정 하 여 **기본**입니다. 각 진단의에서 볼 수 있는 기본 심각도 합니다 **속성** 창입니다.

다음 스크린샷에서 세 가지 서로 다른 심각도 사용 하 여 코드 편집기에서 세 가지 다른 진단 위반을 보여 줍니다. 물론 구불구불한, 작은 상자 오른쪽의 스크롤 막대의 색을 확인할 수 있습니다.

![코드 편집기에서 오류, 경고 및 정보 위반](media/diagnostics-severity-colors.png)

다음 스크린샷은 동일한 세 위반에 표시 되는 **오류 목록**:

![오류 목록의 오류, 경고 및 정보 위반](media/diagnostics-severities-in-error-list.png)

규칙의 심각도 변경할 수 있습니다 **솔루션 탐색기**, 또는 합니다  *\<projectname >.ruleset* 에서규칙의심각도변경하면솔루션에추가되는파일 **솔루션 탐색기**합니다.

![솔루션 탐색기에서 규칙 집합 파일](media/ruleset-in-solution-explorer.png)

### <a name="set-rule-severity-from-solution-explorer"></a>솔루션 탐색기에서 규칙 심각도 설정

1. **솔루션 탐색기**를 확장 하 고 **참조가** > **분석기** (**종속성**  >  **분석기** .NET Core 프로젝트에 대 한).

1. 심각도 설정 하려는 규칙을 포함 하는 어셈블리를 확장 합니다.

1. 선택한 규칙을 마우스 오른쪽 단추로 클릭 **규칙 집합 심각도 설정**합니다. 플라이 아웃 메뉴에서 심각도 옵션 중 하나를 선택 합니다.

   규칙 심각도 활성 규칙 집합 파일에 저장 됩니다.

### <a name="set-rule-severity-in-the-rule-set-file"></a>규칙 집합 파일의 규칙 심각도 설정

1. 열기는 [규칙 집합](analyzer-rule-sets.md) 파일에서 두 번 클릭 하 여 **솔루션 탐색기**을 선택 하면 **활성 규칙 집합 열기** 오른쪽 클릭 메뉴에는 **분석기** 노드를 선택 하 여 **열려** 에 **코드 분석** 프로젝트 속성 페이지.

1. 포함 된 어셈블리를 확장 하 여 규칙을 찾습니다.

1. 에 **동작** 열에서 드롭다운 목록을 열고 값을 선택 하 고 목록에서 원하는 심각도 선택 합니다.

   ![규칙 집합 파일을 편집기에서 열기](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>위반 표시 안 함

여러 가지 방법으로 규칙 위반을 표시 하지 않을 수 있습니다.

- **분석** 메뉴

  선택 **분석** > **코드 분석 실행 및 활성 문제를 표시 하지 않으려면** 모든 현재 위반 하지 않으려면 메뉴 모음에서. 이 때때로 "기준 설정" 이라고 합니다.

- **솔루션 탐색기**

  위반 하지 않으려면 **솔루션 탐색기**, 규칙의 심각도 **None**합니다.

- **규칙 집합 편집기**

  규칙 집합 편집기에서 위반을 표시 하지 않으려면 해당 이름 옆에 있는 확인란의 선택을 취소 하거나 설정 **동작** 하 **None**합니다.

- **코드 편집기**

  코드 편집기에서 위반을 표시 하지 않으려면 위반 및 키를 눌러 코드 줄에 커서를 놓고 **Ctrl**+**합니다.** 열려는 합니다 **빠른 작업** 메뉴. 선택 **CAXXXX 표시 안 함** > **억제 파일/소스의**합니다.

  ![빠른 작업 메뉴에서 진단 표시 안 함](media/suppress-diagnostic-from-editor.png)

- **오류 목록**

  하나 이상의 진단 표시 하지 않을 수 있습니다 합니다 **오류 목록** 을 선택 하 여 요소를 표시 하지 않으려면 하 고 마우스 오른쪽 단추로 클릭 한 다음 **표시 안 함** > **에서 Source/In 비 표시 오류 파일**합니다.

  - 무시 하는 경우 **소스**서 **변경 내용 미리 보기** 대화 상자가 열리고의 미리 보기를 표시 합니다 C# [#pragma 경고](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 또는 Visual Basic [#Disable 경고](/dotnet/visual-basic/language-reference/directives/directives) 소스 코드에 추가 되는 지시문입니다.

    ![코드 파일에서 #pragma 경고를 추가 하는 미리 보기](media/pragma-warning-preview.png)

  - 선택 하는 경우 **억제 파일에**의 **변경 내용 미리 보기** 대화 상자가 열리고의 미리 보기를 표시 합니다 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 전역 비 표시 오류 파일에 추가 되는 특성입니다.

    ![SuppressMessage 특성 억제 파일에 추가 하는 미리 보기](media/preview-changes-in-suppression-file.png)

  에 **변경 내용 미리 보기** 대화 상자에서 **적용**합니다.

  > [!NOTE]
  > 표시 되지 않는 경우는 **표시 안 함** 메뉴 옵션에서 **솔루션 탐색기**, 위반 빌드 및 없습니다 실시간 분석에서 가져온 것입니다. 합니다 **오류 목록** 진단 또는 둘 다에서 위반 라이브 코드 분석 및 작성 하는 규칙을 표시 합니다. 빌드 진단 일 수 있으므로 유효 하지 않은 예를 들어, 위반을 수정 하기 위해 코드를 편집 했습니다 해도 다시 작성 하지 않은 경우 억제할 수 없습니다에서 이러한 진단 합니다 **오류 목록**합니다. 실시간 분석 또는 IntelliSense에서 현재 소스를 사용 하 여 항상 최신임 진단과에서 표시 하지 않을 수 있습니다 합니다 **오류 목록**합니다. 제외할 *빌드* 전환 하 고 선택 항목에서 진단을 합니다 **오류 목록** 에서 소스 필터 **빌드 + IntelliSense** 에 **Intellisense만**. 진단 표시 안 함 및 이전에 설명 된 대로 진행 하려면를 선택 합니다.
  >
  > ![Visual Studio의 오류 목록 원본 필터](media/error-list-filter.png)

## <a name="command-line-usage"></a>명령줄 사용법

명령줄에서 프로젝트를 빌드할 때 다음 조건에 해당 하는 경우 규칙 위반 빌드 출력에 나타납니다.

- 분석기는 VSIX 확장 아니라 Nuget 패키지로 설치 됩니다.

- 프로젝트의 코드에서 하나 이상의 규칙을 위반 합니다.

- 합니다 [심각도](#rule-severity) 위반된 규칙의 설정 되어 **경고**, 위반 빌드 실패를 발생 하지는 경우 또는 **오류**, 위반 빌드 실패를 발생 하는 경우.

빌드 출력의 자세한 정도 규칙 위반의 표시 여부에 영향을 주지 않습니다. 있어도 **quiet** 빌드 출력의 자세한 정도 규칙 위반 표시 합니다.

> [!TIP]
> 정적 코드 분석을 사용 하 여 명령줄에서 실행에 익숙한 사용자 라면 *FxCopCmd.exe* 사용 하 여 msbuild를 통해 또는 합니다 **RunCodeAnalysis** 플래그, Roslyn 분석기를 사용 하 여 작업을 수행 하는 방법은 다음과 같습니다.

Msbuild를 사용 하 여 프로젝트를 빌드하면 명령줄 분석기 위반을 보려면, 이와 같은 명령을 실행 합니다.

```cmd
msbuild myproject.csproj /target:rebuild /verbosity:minimal
```

다음 이미지는 분석기 규칙 위반을 포함 하는 프로젝트 개발에 이르기까지 명령줄 빌드 출력을 보여 줍니다.

![규칙 위반을 사용하여 MSBuild 출력](media/command-line-build-analyzers.png)

## <a name="dependent-projects"></a>종속 프로젝트

.NET Core 프로젝트에서 NuGet 분석기를 지정 된 프로젝트에 대 한 참조를 추가 하는 경우 해당 분석기는 자동으로 추가 종속 프로젝트를 너무 합니다. 예를 들어 종속 프로젝트가 단위 테스트 프로젝트를 사용 하는 경우이 동작을 사용 하지 않으려면 private으로 NuGet 패키지를 표시 합니다 *.csproj* 하거나 *.vbproj* 를설정하여참조된프로젝트의파일**PrivateAssets** 특성:

```xml
<PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.9.0" PrivateAssets="all" />
```

## <a name="see-also"></a>참고자료

- [Visual Studio에서 Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [Roslyn 분석기 버그 제출](https://github.com/dotnet/roslyn-analyzers/issues)
- [규칙 집합 사용](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [코드 분석 경고 표시 안 함](../code-quality/in-source-suppression-overview.md)
