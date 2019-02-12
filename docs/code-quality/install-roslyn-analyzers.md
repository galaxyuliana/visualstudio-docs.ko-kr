---
title: Roslyn 분석기 설치
ms.date: 08/03/2018
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
ms.openlocfilehash: de4818a57dc09825e6f41a635ea777a9e3f06e2a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55910513"
---
# <a name="install-net-compiler-platform-analyzers"></a>.NET 컴파일러 플랫폼 분석기 설치

Visual Studio 2017에는.NET 컴파일러 플랫폼의 핵심 집합을 포함 (*Roslyn*) 분석기입니다. 이러한 분석기는 항상 켜져 있습니다. NuGet 패키지 또는에서 Visual Studio 확장으로 추가 분석기를 설치할 수 있습니다 *VSIX* 파일입니다.

## <a name="to-install-nuget-analyzer-packages"></a>NuGet 분석기 패키지를 설치 하려면

1. www.nuget.org 설치 하려는 분석기 패키지를 찾습니다. 예를 들어, 하려는 [Microsoft FxCop 분석기 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package) 특히 보안과 성능 문제에 대 한 코드를 확인 합니다.

2. 사용 하 여 Visual Studio에서 패키지를 설치 합니다 [패키지 관리자 콘솔](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) 또는 [패키지 관리자 UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)합니다.

   > [!NOTE]
   > 각 분석기 패키지에 대 한 www.nuget.org 페이지에 붙여 명령을 표시 합니다 **패키지 관리자 콘솔**합니다. 클립보드에 텍스트를 복사 하는 유용한 단추는 짝수입니다.
   >
   > ![패키지 관리자 콘솔 명령을 표시 하는 NuGet.org 페이지](media/nuget-install-command.png)

   분석기 어셈블리 설치 되 고 나타나지 **솔루션 탐색기** 아래에서 **참조가** > **분석기**합니다.

## <a name="to-install-vsix-analyzers"></a>VSIX 분석기를 설치 하려면

1. Visual Studio에서 선택 **도구가** > **확장 및 업데이트**합니다.

   **확장명 및 업데이트** 대화 상자가 열립니다.

   > [!NOTE]
   > 또는 찾기 및 다운로드할 수 있습니다 분석기 확장에서 직접 [Visual Studio Marketplace](https://marketplace.visualstudio.com)합니다.

2. 확장 **Online** 한 다음 선택한 왼쪽된 창의 **Visual Studio Marketplace**합니다.

3. 검색 상자에를 설치 하려면 분석기 확장의 이름을 입력 합니다. 예를 들어, 하려는 [Microsoft FxCop 분석기 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix) 특히 보안과 성능 문제에 대 한 코드를 확인 합니다.

4. 선택 **다운로드**합니다.

   확장 다운로드 됩니다.

5. 선택 **확인** 대화 상자를 닫은 다음 시작 하려면 Visual Studio의 모든 인스턴스를 닫습니다에 **VSIX 설치 관리자**합니다.

   합니다 **VSIX 설치 관리자** 대화 상자가 열립니다.

   ![Microsoft 코드 분석을 위한 VSIX 설치 관리자](media/vsix-installer-code-analysis.png)

6. 선택 **수정** 설치를 시작 합니다.

7. 2 분 정도 후 설치를 완료 합니다. 선택 **닫기**합니다.

8. Visual Studio를 다시 엽니다.

확장 설치를 선택 하는지 여부를 확인 하려는 경우 **도구가** > **확장 및 업데이트**합니다. 에 **확장 및 업데이트** 대화 상자에서를 **설치 된** 왼쪽의 범주 이름으로 확장 한 다음 검색 합니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [Visual Studio에서 Roslyn 분석기 사용](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [FxCop 분석기 설치](../code-quality/install-fxcop-analyzers.md)