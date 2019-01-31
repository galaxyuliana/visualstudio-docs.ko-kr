---
title: 개발자 테스트 도구
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed3dccb61be21e571deb2bb8475b784e3a981449
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54956014"
---
# <a name="developer-testing-tools-scenarios-and-capabilities"></a>개발자 테스트 도구, 시나리오 및 호환성

유닛 테스트를 사용하여 코드 상태를 유지 관리합니다. Visual Studio는 개발자가 애플리케이션을 테스트할 때 사용할 수 있는 다양하고 효과적인 도구와 기술을 제공합니다.

## <a name="avoid-regressions-and-achieve-code-coverage-with-intellitest"></a>IntelliTest를 사용하여 재발 방지 및 코드 검사 수행

기존 단위 테스트 도구 모음에서 각 테스트 사례는 모범 사용 시나리오를 나타내고 어설션에는 입력과 출력 간 관계가 포함됩니다.  비슷한 몇 가지 시나리오를 확인하는 것으로 충분할 수 있지만, 숙련된 개발자는 올바르지만 테스트되지 않은 입력이 잘못된 응답을 유발할 경우 충분히 테스트된 코드에도 버그가 숨어 있음을 알 수 있습니다.

IntelliTest를 사용하여 검사를 개선하고 재발을 방지합니다. IntelliTest는 새로운 코드나 기존 코드에 대해 단위 테스트를 만들고 유지하기 위한 노력을 대폭 줄여 줍니다.

![작동 중인 IntelliTest](media/devtest-intellitest.png)

* [Introduction to IntelliTest with Visual Studio](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20IntelliTest%20with%20Visual%20Studio%20Enterprise%202015.docx)(Visual Studio의 IntelliTest 소개)
* [IntelliTest - 한 번 테스트로 모두 제어](https://blogs.msdn.microsoft.com/devops/2015/07/05/intellitest-one-test-to-rule-them-all/)
* [IntelliTest 비디오](https://channel9.msdn.com/Series/Test-Tools-in-Visual-Studio)
* [IntelliTest 시작](generate-unit-tests-for-your-code-with-intellitest.md)
* [IntelliTest 참조 설명서](intellitest-manual/index.md)

## <a name="user-interface-testing-with-coded-ui-and-selenium"></a>코딩된 UI 및 Selenium을 사용하여 사용자 인터페이스 테스트

최고 수준 또는 커뮤니티 승인 UI 테스트를 사용하여 UI(사용자 인터페이스)를 테스트합니다. 코딩된 UI 테스트를 통해 완전 자동화된 테스트를 만들어 애플리케이션 사용자 인터페이스 기능과 동작의 유효성을 검사할 수 있습니다. 코딩된 UI 테스트는 XAML 기반 UWP 앱, 브라우저 앱, SharePoint 앱을 포함한 다양한 기술에서 UI 테스트를 자동화할 수 있습니다.

최고 수준의 코딩된 UI 테스트 또는 Selenium을 사용한 제네릭 브라우저 기반 UI 테스트를 선택할지 여부와 관계없이 Visual Studio는 필요한 모든 도구를 제공합니다.

![코딩된 UI를 통해 UI 테스트](media/devtest-codeduitest.png)

* [UI 자동화를 사용하여 코드 테스트](use-ui-automation-to-test-your-code.md)
* [코딩된 UI 테스트 만들기, 편집 및 유지 관리 시작](walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
* [코딩된 UI 테스트를 사용하여 UWP 앱 테스트](test-uwp-app-with-coded-ui-test.md)
* [코딩된 UI 테스트를 사용하여 SharePoint 애플리케이션 테스트](testing-sharepoint-2010-applications-with-coded-ui-tests.md)
* [Visual Studio Enterprise의 코딩된 UI 테스트 소개(랩)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20Coded%20UI%20Tests%20with%20Visual%20Studio%20Enterprise%202015.docx)

## <a name="effective-unit-testing-with-visual-studio-code-coverage"></a>Visual Studio 코드 검사를 사용한 효과적인 유닛 테스트

프로젝트의 코드 중 단위 테스트와 같은 코딩된 테스트를 사용하여 실제로 테스트할 부분을 결정하려면 Visual Studio의 코드 검사 기능을 사용합니다. 버그로부터 효과적으로 보호하려면 코드의 상당한 부분을 실행 또는 ‘검사’해야 합니다.

코드 검사 분석은 관리되는 코드와 관리되지 않은(네이티브) 코드에 적용할 수 있습니다.

테스트 탐색기를 사용하여 테스트 메서드를 실행하는 경우 코드 검사는 선택 사항입니다. 결과 테이블에는 각 어셈블리, 클래스 및 메서드에서 실행되는 코드의 백분율이 표시됩니다. 또한 소스 편집기에는 테스트된 코드가 표시됩니다.

* [코드 검사를 사용하여 테스트할 코드 범위 결정](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Visual Studio의 유닛 테스트, 코드 검사 및 코드 복제본 분석(랩)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [코드 검사 분석 사용자 지정](customizing-code-coverage-analysis.md)

## <a name="test-explorer"></a>테스트 탐색기

**테스트 탐색기**를 통해 개발자는 단위 테스트를 만들고, 관리하고, 실행할 수 있습니다.

![Visual Studio 테스트 탐색기](media/devtest-testexplorer.png)

* [유닛 테스트 시작](unit-test-your-code.md)
* [테스트 탐색기를 사용하여 단위 테스트 실행](run-unit-tests-with-test-explorer.md)
* [테스트 탐색기 FAQ](test-explorer-faq.md)
* [타사 단위 테스트 프레임워크 설치](install-third-party-unit-test-frameworks.md)

Visual Studio는 확장 가능하고 이제 NUnit 및 xUnit.net과 같은 타사 유닛 테스트 어댑터에도 사용할 수 있습니다. 또한 코드 복제본 기능은 일반적인 버그 수정 또는 리팩터링의 후보가 될 수 있는 의미상 비슷한 코드 블록을 식별하도록 지원함으로써 고품질 소프트웨어 제공과 관련되어 있습니다.

![타사 테스트 통합](media/devtest-thirdparty.png)

## <a name="see-also"></a>참고 항목

* [유닛 테스트 시작](getting-started-with-unit-testing.md)
* [Team Foundation Server의 단위 테스트 실행 시간 단축](https://blogs.msdn.microsoft.com/devops/2015/07/30/speeding-up-unit-test-execution-in-tfs/)
* [병렬 및 컨텍스트 단위 테스트 실행](https://blogs.msdn.microsoft.com/devops/2016/02/08/parallel-and-context-sensitive-test-execution-with-visual-studio-2015-update-1/)
* [Visual Studio의 유닛 테스트, 코드 검사 및 코드 복제본 분석(랩)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)
