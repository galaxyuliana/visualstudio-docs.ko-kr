---
title: 종속성 다이어그램의 확장 문제 해결
ms.date: 11/04/2016
ms.topic: troubleshooting
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 431748ee6e9b5ee5b66f19ebed2d7fdaeb3ccb9f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949982"
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>종속성 다이어그램의 확장 문제 해결

이 항목에서는 레이어 모델 확장을 만들 때 발생할 수 있는 몇 가지 문제를 해결합니다.

## <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-visual-studio"></a>My 확장을 디버그 하려면 f5 키를 누르면 내 명령, 제스처 처리기, 유효성 검사 확장 또는 사용자 지정 속성에 나타나지 않습니다 Visual Studio의 실험적 인스턴스에서 종속성 다이어그램

1. Visual Studio의 실험적 인스턴스에서 확장 솔루션을 엽니다는 **빌드할** 메뉴에서 클릭 **솔루션 다시 빌드**합니다.

2. 키를 눌러 **F5** 또는 **ctrl+f5** Visual Studio의 실험적 인스턴스를 시작 합니다. 종속성 다이어그램을 열어 확장을 테스트 합니다.

   필요한 경우 다음 절차를 계속 진행합니다.

## <a name="an-old-version-of-my-extension-runs"></a>이전 버전의 확장이 실행됩니다.

1. Visual Studio의 실험적 인스턴스가 실행 되 고 있는지 확인 하십시오.

2. 폴더를 삭제 합니다: %LocalAppData%\Microsoft\VisualStudio\\[version] \ComponentModelCache

   > [!NOTE]
   > % LocalAppData %는 일반적으로 *DriveName*: \Users\\*UserName*\AppData\Local입니다.

   필요한 경우 다음 절차를 계속 진행합니다.

## <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>이전 버전의 유효성 검사 결과가 나타나거나, 내 유효성 검사 메서드가 호출되지 않습니다.

1.  Visual Studio의 실험적 인스턴스에서는 **빌드할** 메뉴에서 클릭 **솔루션 정리**합니다. 캐시된 이전 유효성 검사 분석 결과가 지워집니다.

2.  모델의 레이어가 코드 요소와 연결되었는지, 그리고 모델에 종속성 링크가 하나 이상 있는지 확인합니다. 유효성을 검사할 항목이 없는 경우에는 유효성 검사가 호출되지 않습니다.

3.  일반 중단점은 별도 프로세스로 실행되기 때문에 유효성 검사 메서드에서 작동하지 않습니다. 메서드를 단계별로 실행하려는 경우 `System.Diagnostics.Debugger.Launch()` 호출을 삽입해야 합니다.

4.  **source.extension.vsixmanifest** 레이어 유효성 검사 프로젝트에서 모두 추가 되어 있는지 확인 한 **MEF 구성 요소** 항목 및 **사용자 지정 확장 형식** 아래에 있는 항목 **콘텐츠**합니다.

## <a name="see-also"></a>참고 항목

- [종속성 다이어그램 확장](../modeling/extend-layer-diagrams.md)
