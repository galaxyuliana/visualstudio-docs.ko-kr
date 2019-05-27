---
title: FxCop 코드 분석 및 FxCop 분석기
ms.date: 09/06/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis FAQ
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 0415617c5e4106b72cc713f4296b48e94427e6e5
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "66037261"
---
# <a name="frequently-asked-questions-about-fxcop-and-fxcop-analyzers"></a>FxCop 및 FxCop 분석기에 대한 질문과 대답

레거시 FxCop와 FxCop 분석기 간의 차이점을 이해이해하는 것은 다소 혼동을 일으킬 수 있습니다. 이 문서에서는 사용자가 가질 수 있는 일부 질문을 해결하려고 합니다.

## <a name="whats-the-difference-between-legacy-fxcop-and-fxcop-analyzers"></a>레거시 FxCop와 FxCop 분석기 간의 차이점은?

레거시 FxCop는 컴파일된 어셈블리에서 빌드 후 분석을 실행합니다. **FxCopCmd.exe**라는 별도 실행 파일로 실행됩니다. FxCopCmd.exe는 컴파일된 어셈블리를 로드하고, 코드 분석을 실행한 다음, 결과(또는 *진단*)를 보고합니다.

FxCop 분석기는 .NET Compiler Platform("Roslyn")을 기반으로 합니다. 프로젝트 또는 솔루션에서 참조되는 [NuGet 패키지로 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package)합니다. 컴파일러 실행 동안 FxCop 분석기는 소스 코드 기반 분석을 실행합니다. FxCop 분석기는 **csc.exe** 또는 **vbc.exe**의 컴파일러 프로세스 내에서 호스팅되며, 프로젝트가 빌드될 때 분석을 실행합니다. 분석기 결과는 컴파일러 결과와 함께 보고됩니다.

> [!NOTE]
> [Visual Studio 확장으로 FxCop 분석기를 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix)할 수도 있습니다. 이 경우 분석기는 코드 편집기에 입력한 대로 실행하지만 빌드 시 실행하지 않습니다. CI(지속적인 통합)의 일부로 FxCop 분석기를 실행하려는 경우 NuGet 패키지로 대신 설치합니다.

## <a name="does-the-run-code-analysis-command-run-fxcop-analyzers"></a>코드 분석 실행 명령은 FxCop 분석기를 실행하나요?

아니요. **분석** > **코드 분석 실행**을 선택하면 정적 코드 분석 또는 레거시 FxCop를 실행합니다. **코드 분석 실행**은 Roslyn 기반 FxCop 분석기를 포함하여 Roslyn 기반 분석기에 적용되지 않습니다.

## <a name="does-the-runcodeanalysis-msbuild-project-property-run-analyzers"></a>RunCodeAnalysis msbuild 프로젝트 속성은 분석기를 실행하나요?

아니요. 프로젝트 파일에서 **RunCodeAnalysis** 속성(예: *.csproj*)은 레거시 FxCop 실행에만 사용됩니다. **FxCopCmd.exe**를 호출하는 빌드 후 msbuild 작업을 실행합니다. 이는 Visual Studio에서 **분석** > **코드 분석 실행**을 선택하는 것과 같습니다.

## <a name="so-how-do-i-run-fxcop-analyzers-then"></a>그러면 FxCop 분석기를 어떻게 실행하나요?

FxCop 분석기를 실행하려면 먼저 [NuGet 패키지를 설치합니다](install-fxcop-analyzers.md). 그런 다음, Visual Studio에서 또는 msbuild를 사용하여 프로젝트 또는 솔루션을 빌드합니다. FxCop 분석기가 생성하는 경고 및 오류는 **오류 목록** 또는 명령 창에 표시됩니다.

## <a name="i-get-warning-ca0507-even-after-ive-installed-the-fxcop-analyzers-nuget-package"></a>FxCop 분석기 NuGet 패키지를 설치한 후에도 경고 CA0507이 표시됨

FxCop 분석기를 설치했지만 경고 CA0507 **""코드 분석 실행"이 더 이상 사용되지 않고 대신 FxCop 분석기가 빌드 중 실행됩니다."** 가 계속 표시되는 경우에는 프로젝트 파일에서 **RunCodeAnalysis** msbuild 속성을 **false**로 설정해야 할 수 있습니다. 이렇게 설정하지 않으면 각 빌드 후에 정적 코드 분석이 실행됩니다.

```xml
<RunCodeAnalysis>false</RunCodeAnalysis>
```

## <a name="which-rules-have-been-ported-to-fxcop-analyzers"></a>규칙은 FxCop 분석기에 이식 되었으며?

에 대 한 정적 코드 분석 규칙에 이식 되었으며 자세한 [FxCop 분석기](install-fxcop-analyzers.md)를 참조 하십시오 [Fxcop 규칙 포트 상태](fxcop-rule-port-status.md)합니다.

## <a name="see-also"></a>참고자료

- [.NET Compiler Platform 분석기 개요](roslyn-analyzers-overview.md)
- [분석기 시작](fxcop-analyzers.yml)
- [FxCop 분석기 설치](install-fxcop-analyzers.md)
