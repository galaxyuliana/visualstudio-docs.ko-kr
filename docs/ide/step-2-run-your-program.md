---
title: '2단계: 프로그램 실행'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9a8fe90e-c97b-4e98-b6c8-0c6b3962c49d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 74f6d64d515ac7fab454b123686e671d9bcd1d2d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918923"
---
# <a name="step-2-run-your-program"></a>2단계: 프로그램 실행
새 솔루션을 만들면서 실행되는 프로그램을 실제로 빌드했습니다. 이 프로그램은 아직 많은 작업을 수행하지 않고 단순히 제목 표시줄에 **Form1**이 표시된 빈 창만 표시하지만 실행되고 있는 프로그램이 맞습니다.

![비디오 링크](../data-tools/media/playvideo.gif) 이 항목의 비디오 버전은 [자습서 1: Visual Basic에서 비디오 보기 만들기 - 비디오1](http://go.microsoft.com/fwlink/?LinkId=205209) 또는 [자습서 1: C#에서 그림 보기 만들기 - 자습서 1](http://go.microsoft.com/fwlink/?LinkId=205199)을 참조하세요. 이러한 비디오에서는 이전 버전의 Visual Studio를 사용하므로 일부 메뉴 명령과 기타 사용자 인터페이스 요소가 약간 다를 수 있습니다. 그러나 개념 및 절차는 Visual Studio의 현재 버전에서 비슷하게 작동합니다.

## <a name="to-run-your-program"></a>프로그램을 실행하려면

1. 다음 메서드 중 하나를 사용해서 프로그램을 실행합니다.

    - **F5** 키를 선택합니다.

    - 메뉴 모음에서 **디버그** > **디버깅 시작**을 차례로 선택합니다.

    - 도구 모음에서 **디버깅 시작** 단추를 선택하면 다음과 같이 표시됩니다.

         ![디버깅 시작 도구 모음 단추](../ide/media/express_icondebug.png)
**디버깅 시작** 도구 모음 단추

2. Visual Studio에서 프로그램이 실행되고 **Form1** 창이 표시됩니다. 다음 그림에서는 방금 빌드한 프로그램을 보여 줍니다. 이 프로그램은 현재 실행 중이며, 더 많은 기능이 추가될 예정입니다.

     ![실행 중인 Windows Form 애플리케이션](../ide/media/express_firstrun.png)
실행 중인 **Windows Forms** 애플리케이션

3. Visual Studio IDE(통합 개발 환경)으로 돌아가서 새 도구 모음을 살펴봅니다. 프로그램을 실행하면 추가 단추가 도구 모음에 나타납니다. 이러한 단추를 사용하면 프로그램 중지 및 시작과 같은 작업을 수행할 수 있으며 발생할 수 있는 모든 오류(버그)를 추적할 수 있습니다. 이 예제에서는 프로그램을 시작하고 중지하는 데에만 이를 사용하도록 합니다.

     ![디버깅 도구 모음](../ide/media/express_debugtoolbar.png)
**디버깅** 도구 모음

4. 다음 메서드 중 하나를 사용해서 프로그램을 중지합니다.

    - 도구 모음에서 **디버깅 중지** 단추를 선택합니다.

    - 메뉴 모음에서 **디버그** > **디버깅 중지**를 차례로 선택합니다.

    - **Form1** 창의 위쪽 모퉁이에 있는 **X** 단추를 선택합니다.

    > [!NOTE]
    > IDE 안에서 프로그램을 실행할 때는 주로 프로그램에서 버그(오류)를 찾고 수정하는 작업을 수행하기 때문에 IDE 안에서 프로그램을 실행하는 것을 디버깅이라고 합니다. 이 프로그램은 크기가 작고 아직 아무것도 실제로 수행하지는 않지만 마찬가지로 실제 프로그램입니다. 다른 프로그램도 동일한 절차에 따라 실행하고 디버깅합니다. 디버깅에 대한 자세한 내용은 [디버거 소개](../debugger/debugger-feature-tour.md)를 참조하세요.

## <a name="to-continue-or-review"></a>계속하거나 검토하려면

- 다음 자습서 단계로 이동하려면 [3단계: 폼 속성 설정](../ide/step-3-set-your-form-properties.md)을 참조하세요.

- 이전 자습서 단계로 돌아가려면 [1단계: Windows Forms 애플리케이션 프로젝트 만들기](../ide/step-1-create-a-windows-forms-application-project.md)를 참조하세요.
