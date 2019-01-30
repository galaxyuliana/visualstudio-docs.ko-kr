---
title: 타사 단위 테스트 프레임워크 설치
ms.date: 06/07/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 4cf2635cf46b1fa8b395cb8a7cab8769ae6ed6d3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960116"
---
# <a name="install-unit-test-frameworks"></a>단위 테스트 프레임워크 설치

Visual Studio 테스트 탐색기는 탐색기의 어댑터 인터페이스를 개발한 단위 테스트 프레임워크를 실행할 수 있습니다. 프레임워크 설치 프로그램은 이진 파일을 설치하고, 지원하는 언어의 Visual Studio 프로젝트 템플릿을 추가합니다. 템플릿으로 프로젝트를 만들면 프레임워크가 테스트 탐색기에 등록됩니다. Visual Studio 솔루션에는 다양한 프레임워크를 사용하고 다양한 언어로 대상이 지정되는 단위 테스트 프로젝트가 포함될 수 있습니다. 테스트 탐색기는 이들 모두를 실행합니다.

[MSTest](getting-started-with-unit-testing.md)는 Visual Studio에서 제공하는 테스트 프레임워크이며 기본적으로 Visual Studio와 함께 설치됩니다.

## <a name="acquire-frameworks"></a>프레임워크 취득

Visual Studio 확장 관리자 또는 [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)를 사용하여 타사 단위 테스트 프레임워크를 다운로드하고 설치할 수 있습니다. 프레임워크 웹 사이트와 같은 다른 사이트에서도 프레임워크를 다운로드할 수 있습니다.

### <a name="install-from-visual-studio"></a>Visual Studio에서 설치

1. 표준 메뉴에서 **도구**를 선택하고 **확장명 및 업데이트**를 선택합니다.

2. **온라인** > **Visual Studio Marketplace** > **도구**를 확장합니다. **테스트**를 선택합니다.

3. 목록에서 프레임워크를 찾습니다.

4. 프레임워크를 선택하고 **다운로드**를 선택합니다.

자세한 내용은 [Visual Studio 확장명 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)을 참조하세요.

### <a name="install-from-the-web"></a>웹에서 설치

관심 있는 프레임워크를 알고 있는 경우:

1. [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)를 엽니다.

2. **찾기** 상자에 프레임워크 이름을 입력합니다.

3. 결과 목록에서 프레임워크를 선택하여 해당 도구의 **Visual Studio Marketplace** 페이지로 이동합니다.

다른 테스트 도구와 프레임워크 목록을 찾아보려면:

1. [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)를 엽니다.

2. **범주/컬렉션으로 필터링**에서 **모두 보기**를 선택합니다.

3. **범주** 목록(**표시 중**으로 레이블 지정됨)에서 **도구** 노드를 확장하고 **테스트**를 선택합니다.

4. 결과 목록에서 프레임워크를 선택하여 해당 도구의 **Visual Studio Marketplace** 페이지로 이동합니다.

## <a name="update-to-the-latest-test-adapters"></a>최신 테스트 어댑터로 업데이트

테스트 검색 및 실행을 향상하려면 안정적인 최신 테스트 어댑터로 업데이트합니다. MSTest, NUnit 및 xUnit 테스트 어댑터의 업데이트에 대한 자세한 내용은 [Visual Studio 블로그](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/)를 참조하세요.

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>안정적인 최신 테스트 어댑터 버전으로 업데이트하려면

1. **도구** > **NuGet 패키지 관리자** > **솔루션에 대한 NuGet 패키지 관리**로 이동하여 솔루션에 대한 Nuget 패키지 관리자를 엽니다.

2. **업데이트** 탭을 클릭하고 설치된 MSTest, NUnit 또는 xUnit 테스트 어댑터를 검색합니다.

3. 각 테스트 어댑터를 선택한 다음, 드롭다운 메뉴에서 안정적인 최신 버전을 선택합니다.

4. **설치** 단추를 선택합니다.

   ![테스트 어댑터 업그레이드](media/install-adapter-upgrade.png)

## <a name="see-also"></a>참고 항목

- [코드 단위 테스트](../test/unit-test-your-code.md)
