---
title: 분석기 규칙 심각도 및 비 표시
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
ms.openlocfilehash: 6362d3f14065aaf9661e85266753642e4201ca48
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69548042"
---
# <a name="use-code-analyzers"></a>코드 분석기 사용

.NET Compiler Platform ("Roslyn") 코드 분석기는 사용자 C# 가 입력할 때 또는 Visual Basic 코드를 분석 합니다. 각 *진단* 또는 규칙은 프로젝트에 대해 덮어쓸 수 있는 기본 심각도 및 비 표시 상태를 포함 합니다. 이 문서에서는 규칙 심각도 설정, 규칙 집합 사용 및 위반 억제에 대해 설명 합니다.

## <a name="analyzers-in-solution-explorer"></a>솔루션 탐색기의 분석기

**솔루션 탐색기**에서 analyzer 진단의 사용자 지정을 대부분 수행할 수 있습니다. [분석기](../code-quality/install-roslyn-analyzers.md) 를 NuGet 패키지로 설치 하는 경우 **솔루션 탐색기**의 **참조** 또는 **종속성** 노드 아래에 **분석기** 노드가 나타납니다. 분석기를 확장한 다음 분석기 어셈블리 중 하나를 확장 하면 어셈블리에 모든 진단이 표시 됩니다.

![솔루션 탐색기의 분석기 노드](media/analyzers-expanded-in-solution-explorer.png)

**속성** 창에서 설명 및 기본 심각도를 포함 하 여 진단 속성을 볼 수 있습니다. 속성을 보려면 해당 규칙을 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 하거나 규칙을 선택 하 고 **Alt**+**enter**를 누릅니다.

![속성 창의 진단 속성](media/analyzer-diagnostic-properties.png)

진단에 대 한 온라인 설명서를 보려면 진단을 마우스 오른쪽 단추로 클릭 하 고 **도움말 보기**를 선택 합니다.

**솔루션 탐색기** 의 각 진단 옆에 있는 아이콘은 편집기에서 열 때 규칙 집합에 표시 되는 아이콘에 해당 합니다.

- 원의 "i"는 **정보의** [심각도](#rule-severity) 를 나타냅니다.
- 삼각형의 "!"는 **경고** 의 [심각도](#rule-severity) 를 나타냅니다.
- 원의 "x"는 **오류의** [심각도](#rule-severity) 를 나타냅니다.
- 옅은 색 배경의 원에 있는 "i"는 **숨겨진** 의 [심각도](#rule-severity) 를 나타냅니다.
- 원의 아래쪽 화살표는 진단이 억제 됨을 나타냅니다.

![솔루션 탐색기의 진단 아이콘](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>규칙 집합

[규칙 집합](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) 은 개별 진단의 심각도 및 비 표시 상태를 저장 하는 XML 파일입니다.

> [!NOTE]
> 규칙 집합에는 레거시 분석과 코드 분석기의 규칙이 모두 포함 될 수 있습니다.

규칙 집합 편집기에서 활성 규칙 집합을 편집 하려면 **솔루션 탐색기** 의 **참조** > **분석기** 노드를 마우스 오른쪽 단추로 클릭 하 고 **활성 규칙 집합 열기**를 선택 합니다. 규칙 집합을 처음 편집 하는 경우 Visual Studio는 기본 규칙 집합 파일의 복사본을 만들고이를  *\<projectname >* 의 이름을로 설정 하 고 프로젝트에 추가 합니다. 또한이 사용자 지정 규칙 집합은 프로젝트에 대 한 활성 규칙 집합이 됩니다.

프로젝트에 대 한 활성 규칙 집합을 변경 하려면 프로젝트 속성의 **코드 분석** 탭으로 이동 합니다. **이 규칙 집합 실행**의 목록에서 규칙 집합을 선택 합니다. 규칙 집합을 열려면 **열기**를 선택 합니다.

> [!NOTE]
> .NET Core 및 .NET Standard 프로젝트는 **솔루션 탐색기**에서 규칙 집합에 대 한 메뉴 명령을 지원 하지 않습니다 (예: **활성 규칙 집합 열기**). .NET Core 또는 .NET Standard 프로젝트에 대해 기본이 아닌 규칙 집합을 지정 하려면 프로젝트 파일에 [ **CodeAnalysisRuleSet** 속성](using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project) 을 수동으로 추가 합니다. Visual Studio 규칙 집합 편집기 UI의 규칙 집합 내에서 규칙을 계속 구성할 수 있습니다.

## <a name="rule-severity"></a>규칙 심각도

분석기를 NuGet 패키지로 [설치](../code-quality/install-roslyn-analyzers.md) 하는 경우 분석기 규칙의 심각도 또는 *진단을*구성할 수 있습니다. 다음 표에서는 진단의 심각도 옵션을 보여 줍니다.

|Severity|빌드 타임 동작|편집기 동작|
|-|-|-|
|Error|위반은 **오류 목록** 및 명령줄 빌드 출력에 *오류로* 표시 되 고 빌드가 실패 합니다.|잘못 된 코드는 빨강 물결 모양의 밑줄로 표시 되 고 스크롤 막대에 작은 빨간색 상자로 표시 됩니다.|
|경고|위반은 **오류 목록** 및 명령줄 빌드 출력에 *경고* 로 표시 되지만 빌드가 실패 하지는 않습니다.|잘못 된 코드는 녹색 물결 모양의 밑줄로 표시 되 고 스크롤 막대의 작은 녹색 상자로 표시 됩니다.|
|정보|위반은 명령줄 빌드 출력이 아닌 **오류 목록**의 *메시지로* 표시 됩니다.|잘못 된 코드는 회색 물결 모양의 밑줄로 표시 되 고 스크롤 막대의 작은 회색 상자로 표시 됩니다.|
|숨김|사용자에 게 표시 되지 않습니다.|사용자에 게 표시 되지 않습니다. 그러나 진단이 IDE 진단 엔진에 보고 됩니다.|
|없음|완전히 표시 되지 않습니다.|완전히 표시 되지 않습니다.|

또한 **기본값**을 설정 하 여 규칙의 심각도를 "다시 설정" 할 수 있습니다. 각 진단에는 **속성** 창에 표시 될 수 있는 기본 심각도가 있습니다.

다음 스크린샷에서는 세 가지 심각도가 있는 코드 편집기의 세 가지 진단 위반을 보여 줍니다. 물결 모양의 색 뿐만 아니라 오른쪽에 있는 스크롤 막대의 작은 상자도 확인 합니다.

![코드 편집기에서 오류, 경고 및 정보 위반](media/diagnostics-severity-colors.png)

다음 스크린샷은 **오류 목록**에 표시 되는 것과 동일한 세 가지 위반을 보여 줍니다.

![오류 목록에서 오류, 경고 및 정보 위반](media/diagnostics-severities-in-error-list.png)

**솔루션 탐색기**규칙의 심각도를 변경한 후 솔루션에 추가 된 **솔루션 탐색기**또는  *\<projectname >* 에서 규칙의 심각도를 변경할 수 있습니다.

![솔루션 탐색기의 규칙 집합 파일](media/ruleset-in-solution-explorer.png)

### <a name="set-rule-severity-from-solution-explorer"></a>솔루션 탐색기에서 규칙 심각도 설정

1. **솔루션 탐색기**에서 **참조** > **분석기** (.net Core 프로젝트에 대 한**종속성** > **분석기** )를 확장 합니다.

1. 심각도를 설정 하려는 규칙이 포함 된 어셈블리를 확장 합니다.

1. 규칙을 마우스 오른쪽 단추로 클릭 하 고 **규칙 집합 심각도 설정**을 선택 합니다. 플라이 아웃 메뉴에서 심각도 옵션 중 하나를 선택 합니다.

   규칙에 대 한 심각도는 활성 규칙 집합 파일에 저장 됩니다.

### <a name="set-rule-severity-in-the-rule-set-file"></a>규칙 집합 파일에 규칙 심각도 설정

1. **솔루션 탐색기**에서 [규칙 집합](analyzer-rule-sets.md) 파일을 두 번 클릭 하거나 **분석기** 노드의 오른쪽 클릭 메뉴에서 **활성 규칙 집합 열기** 를 선택 하거나에 대 한 **코드 분석** 속성 페이지에서 **열기** 를 선택 하 여 규칙 집합 파일을 엽니다. 프로젝트입니다.

1. 포함 하는 어셈블리를 확장 하 여 규칙을 찾습니다.

1. **작업** 열에서 값을 선택 하 여 드롭다운 목록을 열고 목록에서 원하는 심각도를 선택 합니다.

   ![편집기에 열려 있는 규칙 집합 파일](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>위반 표시 안 함

규칙 위반을 표시 하지 않는 방법에는 여러 가지가 있습니다.

- **분석** 메뉴에서

  메뉴 모음에서 **분석** > **실행 코드 분석 및 활성 문제 표시 안 함** 을 선택 하 여 현재 위반을 모두 표시 하지 않습니다. 이를 "기준 기준선"이 라고도 합니다.

- **솔루션 탐색기** 에서

  **솔루션 탐색기**위반을 억제 하려면 규칙의 심각도를 **None**으로 설정 합니다.

- **규칙 집합 편집기** 에서

  규칙 집합 편집기에서 위반을 억제 하려면 해당 이름 옆의 확인란을 선택 취소 하거나 **작업** 을 **없음**으로 설정 합니다.

- **코드 편집기** 에서

  코드 편집기에서 위반을 방지 하려면 코드 줄에 위반이 있는 커서를 놓고 **ctrl**+키를 누릅니다 **.** 를 실행 하 여 **빠른 작업** 메뉴를 엽니다. **원본/비**표시 제거 파일에서 >  **caxxxx를 표시 하지 않습니다**.를 선택 합니다.

  ![빠른 작업 메뉴에서 진단 표시 안 함](media/suppress-diagnostic-from-editor.png)

- **오류 목록** 에서

  표시 하지 않을 항목을 선택 하 여 **오류 목록** 에서 하나 이상의 진단을 표시 하지 않고 마우스 오른쪽 단추를 클릭 한 다음**소스/비**표시 제거 파일에서 **표시 안 함** > 을 선택 하 여 하나 이상의 진단을 표시 하지 않을 수 있습니다.

  - **소스에서**표시 하지 않는 경우 **변경 내용 미리 보기** 대화 상자가 열리고 소스 코드에 추가 C# 된 [#pragma 경고](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 또는 Visual Basic [#Disable 경고](/dotnet/visual-basic/language-reference/directives/directives) 지시문의 미리 보기가 표시 됩니다.

    ![코드 파일에 #pragma 경고 추가의 미리 보기](media/pragma-warning-preview.png)

  - **비 표시 오류 (Suppression) 파일에서**를 선택 하면 **변경 내용 미리 보기** 대화 상자가 열리고 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 전역 비 표시 오류 파일에 추가 된 특성의 미리 보기가 표시 됩니다.

    ![SuppressMessage 특성을 비 표시 오류 (suppression) 파일에 추가 하는 미리 보기](media/preview-changes-in-suppression-file.png)

  **변경 내용 미리 보기** 대화 상자에서 **적용**을 선택 합니다.

  > [!NOTE]
  > **솔루션 탐색기**에 **표시 안 함** 메뉴 옵션이 표시 되지 않는 경우에는 위반이 발생 했을 수 있습니다. **오류 목록** 는 라이브 코드 분석과 빌드 모두에서 진단 또는 규칙 위반을 표시 합니다. 빌드 진단은 부실 할 수 있습니다. 예를 들어 위반 문제를 해결 하기 위해 코드를 편집 했지만 다시 빌드하지 않은 경우에는 **오류 목록**에서 이러한 진단을 표시 하지 않을 수 있습니다. 라이브 분석 또는 IntelliSense의 진단은 항상 최신 원본으로 최신 상태를 유지 하며 **오류 목록**에서 표시 되지 않을 수 있습니다. 선택에서 *빌드* 진단을 제외 하려면 **빌드 + Intellisense** 에서 **intellisense 전용**으로 **오류 목록** 원본 필터를 전환 합니다. 그런 다음 앞에서 설명한 대로 표시 하지 않을 진단을 선택 하 고 계속 진행 합니다.
  >
  > ![Visual Studio에서 원본 필터 오류 목록](media/error-list-filter.png)

## <a name="command-line-usage"></a>명령줄 사용

명령줄에서 프로젝트를 빌드하는 경우 다음 조건이 충족 되 면 빌드 출력에 규칙 위반이 표시 됩니다.

- 분석기는 VSIX 확장이 아니라 Nuget 패키지로 설치 됩니다.

- 프로젝트 코드에서 하나 이상의 규칙을 위반 했습니다.

- 위반 된 규칙의 [심각도](#rule-severity) 는 **경고**로 설정 되며,이 경우 위반으로 인해 빌드가 실패 하거나 **오류가**발생 하지 않습니다 .이 경우 위반으로 인해 빌드가 실패 합니다.

빌드 출력의 자세한 정도는 규칙 위반이 표시 되는지 여부에 영향을 주지 않습니다. **자동** 자세한 정도를 사용 하더라도 규칙 위반은 빌드 출력에 표시 됩니다.

> [!TIP]
> *FxCopCmd* 또는 **runcodeanalysis** 플래그를 사용 하 여 msbuild를 통해 명령줄에서 레거시 분석을 실행 하는 데 익숙한 경우 코드 분석기를 사용 하 여이 작업을 수행 하는 방법은 다음과 같습니다.

Msbuild를 사용 하 여 프로젝트를 빌드할 때 명령줄에서 분석기 위반을 확인 하려면 다음과 같이 명령을 실행 합니다.

```cmd
msbuild myproject.csproj /target:rebuild /verbosity:minimal
```

다음 이미지는 분석기 규칙 위반을 포함 하는 프로젝트를 빌드할 때의 명령줄 빌드 출력을 보여 줍니다.

![규칙 위반을 사용하여 MSBuild 출력](media/command-line-build-analyzers.png)

## <a name="dependent-projects"></a>종속 프로젝트

.NET Core 프로젝트에서 NuGet 분석기를 포함 하는 프로젝트에 대 한 참조를 추가 하면 해당 분석기도 자동으로 종속 프로젝트에 추가 됩니다. 이 동작을 사용 하지 않도록 설정 하려면 예를 들어, 종속 프로젝트가 단위 테스트 프로젝트인 경우 **PrivateAssets** 특성을 설정 하 여 참조 된 프로젝트의 *.csproj* 또는 *.vbproj* 파일에서 NuGet 패키지를 private으로 표시 합니다.

```xml
<PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.9.0" PrivateAssets="all" />
```

## <a name="see-also"></a>참고자료

- [Visual Studio의 코드 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [코드 분석기 버그 제출](https://github.com/dotnet/roslyn-analyzers/issues)
- [규칙 집합 사용](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [코드 분석 경고 표시 안 함](../code-quality/in-source-suppression-overview.md)
