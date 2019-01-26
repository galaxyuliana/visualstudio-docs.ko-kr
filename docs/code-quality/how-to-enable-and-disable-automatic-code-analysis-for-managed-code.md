---
title: 코드 분석을 사용할지 설정 합니다.
ms.date: 10/25/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 32987a8008638b13606c3eb14cb023ded2741998
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54973943"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>방법: 관리 코드에 대 한 자동 코드 분석 활성화 및 비활성화

관리 코드 프로젝트의 각 빌드 후 실행할 (정적) 코드 분석을 구성할 수 있습니다. 있습니다 수 다른 코드를 각 빌드 구성에 대 한 분석 속성 설정, 예를 들어, 디버그 및 릴리스 합니다.

이 문서에만 정적 코드 분석 및 사용 하 여 하지 라이브 코드 분석 적용 됩니다 [Roslyn 코드 분석기](roslyn-analyzers-overview.md)합니다.

## <a name="to-enable-or-disable-automatic-code-analysis"></a>자동 코드 분석을 사용할지 설정 합니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.

1. 프로젝트에 대 한 속성 대화 상자를 선택 합니다 **코드 분석** 탭 합니다.

   > [!TIP]
   > .NET Core 및.NET Standard 응용 프로그램은 같은 최신 프로젝트 형식에 **코드 분석** 탭 합니다. 정적 코드 분석을 이러한 프로젝트 형식에 대 한 제공 되지 않지만 여전히 사용 하 여 라이브 코드 분석을 얻을 수 있습니다 [Roslyn 코드 분석기](roslyn-analyzers-overview.md)합니다. Roslyn 코드 분석기에서 발생 한 경고를 표시 하지 않으려면이 문서의 뒷부분에 나오는 참고를 참조 하세요.

1. 빌드 형식 지정 **Configuration** 및 대상 플랫폼 **플랫폼**합니다.

1. 를 사용 하거나 자동 코드 분석을 사용 하지 않도록 설정 하려면 선택 하거나 선택을 취소 합니다 **빌드에 코드 분석 사용** 확인란 합니다.

> [!NOTE]
> 합니다 **빌드에 코드 분석 사용** 확인란 정적 코드 분석에만 영향을 줍니다. 영향을 미치지 [Roslyn 코드 분석기](roslyn-analyzers-overview.md)는 NuGet 패키지로 설치한 경우 빌드 시 항상 실행 합니다. 분석기 오류를 해제 하려는 경우는 **오류 목록**를 선택 하 여 모든 현재 위반을 무시할 수 있습니다 **분석** > **코드 분석 실행 및 활성 표시 안 함 문제** 메뉴 모음에서. 자세한 내용은 [위반을 표시 하지 않으려면](use-roslyn-analyzers.md#suppress-violations)합니다.
