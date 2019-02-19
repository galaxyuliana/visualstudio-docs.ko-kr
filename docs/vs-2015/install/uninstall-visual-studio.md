---
title: Visual Studio 2015 제거 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- uninstalling
- uninstalling visual studio
- uninstall
- uninstall Visual Studio
ms.assetid: 0e445255-b796-426d-ad93-a4d8e36da2c5
caps.latest.revision: 9
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: b84cff997e24882903abae048dbdd5c3c16f7e17
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54834831"
---
# <a name="uninstall-visual-studio"></a>Visual Studio 제거
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017에 대 한 최신 설명서를 참조 하세요 [Visual Studio 2017 제거](https://docs.microsoft.com/visualstudio/install/uninstall-visual-studio)합니다.

이 페이지는 이전 버전의 개발자 용 생산성 도구가 통합된 제품군의 Visual Studio 2015를 제거 하는 과정을 보여 줍니다.

##  <a name="uninstalling"></a>
#### <a name="to-uninstall-visual-studio-by-using-the-standard-uninstallation-method"></a>"표준" 제거 방법을 사용 하 여 Visual Studio를 제거 하려면

1. **제어판**의 **프로그램 및 기능** 페이지에서 제거할 제품 버전을 선택한 다음, **변경**을 선택합니다.

2. 설치 마법사에서 **제거**, **예**를 차례로 선택한 다음, 마법사의 나머지 지시를 따릅니다.

   이 표준 또는 기본 방법을 남습니다 일부 Visual Studio를 처음 설치 (예를 들어는 Microsoft.NET Framework, Microsoft Visual c + + 재배포 가능 패키지, Microsoft SQL Server 등)의 첫 번째 설치 되었던 항목입니다.   다른 여러 응용 프로그램에 종속 되어 있으므로 설치 상태로 유지 합니다. 하지만 항목도 제거 하려는 경우 해당 항목을 선택 **프로그램 및 기능**, 각각 개별적으로 제거 합니다.

#### <a name="to-uninstall-visual-studio-and-all-other-related-files-that-is-to-uninstall-almost-everything"></a>Visual Studio 및 다른 모든 관련된 파일을 제거 하려면 (즉, 거의 모든 항목을 제거 하려면)

1.  Visual Studio.exe 파일을 찾습니다 (예를 들어, "vs_enterprise.exe" 찾습니다).

    > [!NOTE]
    >  예를 들어 파일 "%ProgramData%\Package Cache"의 하위 폴더 여야 합니다: C:\ProgramData\Package 캐시\\{37e19555-e88d-4aed-9d42-82d0784d2b79} \vs_enterprise.exe

2.  사용 하 여.exe 파일을 실행 합니다 /uninstall /force 명령줄 매개 변수입니다.

     예를 들어 실행 ```vs_enterprise.exe /uninstall /force```, Visual Studio 및 남겨 지는 핵심 구성 요소는 대부분 기본 제거 시 제거 됩니다입니다. 그러나는 제거 하지는 모든 추가 콘텐츠는 Visual Studio 추가 기능 및 확장 (예를 들어, Visual Studio 업데이트 및 기타 선택적인 구성 요소)에 설치할 수 있습니다.

    > [!TIP]
    > 사용할 수 있습니다는 "**전체 제거 프로그램**" 모든 Visual Studio를 제거할 도구 또는 Visual Studio에 업데이트가 설치 될 수 있습니다. 즉, 모든 버전의 Visual Studio 2013 이상. 자세한 참조를 [Visual Studio 제거 프로그램 도구](https://github.com/Microsoft/VisualStudioUninstaller/releases) github입니다.

#### <a name="to-uninstall-visual-studio-in-silent-or-passive-modes-that-is-to-uninstall-from-source"></a>자동 또는 수동 모드에서 Visual Studio를 제거 하려면 (즉, 소스에서 제거 하려면)

1.  Visual Studio가 설치된 컴퓨터에서 Windows 명령 프롬프트를 엽니다.

2.  다음 매개 변수를 입력합니다.

     *DVDRoot* \\< 설치 파일\> \</quiet&#124;수동/> [/norestart] / 제거

#### <a name="to-roll-back-to-a-previous-version-or-release-of--visual-studio"></a>이전 버전 또는 Visual Studio 릴리스의 롤백하려면

1. 이 항목에 나열 된 방법 중 하나를 사용 하 여 Visual Studio를 제거 합니다.

   > [!WARNING]
   >  Visual Studio (또는 Visual Studio 업데이트)의 현재 릴리스를 제거 하 고 다음 이전 릴리스를 설치할 예상 대로 작동 하지 않을 수 있습니다.
   >
   >  결과 종속 버전 또는 릴리스로 Visual Studio를 설치한 후 해당 구성 요소는 버전을 설치할 설치 된 제품 종속 될 수 있는 하거나 Visual Studio 릴리스 또는 구성 요소에의 한 마지막으로, 이전 Visual Studio 버전 하려고 하거나 다시 설치 합니다.  이러한 모든 변수 때문에 표준 제거는 종종 되었던 구성 요소가 Visual Studio 이전 버전 또는 릴리스에서 작동 하지 않을 수 합니다.
   >
   >  따라서 최상의 결과 좋습니다를 사용 하 여 [Visual Studio 제거 프로그램 도구](https://github.com/Microsoft/VisualStudioUninstaller/releases)합니다.

2. 설치 또는 사용 하려는 Visual Studio의 이전 버전을 다시 설치 합니다.

   이전 버전의 Visual Studio를 설치 하는 경우에 설치 프로그램을 최신 버전 사용 또는 사용 가능한 경우 해제 하려고 시도할 수 있습니다. 자세한 내용은 참조는 [방법: 특정 버전의 Visual Studio 설치](../install/how-to-install-a-specific-release-of-visual-studio.md) 항목입니다.

## <a name="see-also"></a>참고 항목
 [Visual Studio 설치](https://msdn.microsoft.com/library/e2h7fzkw.aspx)