---
title: Xamarin을 사용한 디버깅
description: 디버깅은 프로그래밍의 공통적인 필수 부분입니다. 완성도가 높은 IDE인 Mac용 Visual Studio에는 편리한 디버깅을 위한 전체 기능 모음이 포함되어 있습니다. 이 문서에서는 Mac용 Visual Studio에서 안전한 디버깅부터 데이터 시각화까지 디버깅의 잠재력을 완전히 활용하는 방법을 설명합니다.
author: jmatthiesen
ms.author: jomatthi
ms.date: 05/06/2018
ms.technology: vs-ide-debug
ms.assetid: BB7A084D-9AC2-48B5-8076-6C8518796BBA
ms.openlocfilehash: 3578e3e903470f857192643a3da47d62e87da934
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691718"
---
# <a name="debugging-with-xamarin"></a>Xamarin을 사용한 디버깅

Mac용 Visual Studio에 포함된 네이티브 디버거는 Xamarin.iOS, Xamarin.Mac, Xamarin.Android 애플리케이션에 대한 디버깅을 지원합니다.

Mac용 Visual Studio에서는 [*Mono 소프트 디버거*](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger/)를 사용합니다. 이 디버거는 Mono 런타임에 구현되어, Mac용 Visual Studio에서 모든 플랫폼의 관리 코드를 디버그할 수 있게 해줍니다.

## <a name="the-debugger"></a>디버거

Mac용 Visual Studio에서는 Mono 소프트 디버거를 사용하여 모든 Xamarin 애플리케이션의 관리(C# 또는 F#) 코드를 디버그합니다. Mono 소프트 디버거는 Mono 런타임에 기본 제공되는 협조적인 디버거란 점에서 기본 디버거와 다릅니다. 생성된 코드와 Mono 런타임이 IDE와 함께 작동하여 디버깅 경험을 제공합니다. Mono 런타임은 유선 프로토콜을 통해 디버깅 기능을 공개합니다. 자세한 내용은 [Mono 설명서](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger-wire-format/)를 참조하세요.

[LLDB]( http://lldb.llvm.org/index.html) 또는 [GDB]( https://www.gnu.org/software/gdb/)와 같은 하드 디버거는 디버그된 프로그램의 정보나 협조 없이 프로그램을 제어하지만, 네이티브 iOS 또는 Android 코드를 디버그해야 하는 경우 Xamarin 애플리케이션을 디버그할 때 유용할 수 있습니다.

## <a name="using-the-debugger"></a>디버거 사용

애플리케이션 디버그를 시작하려면 구성이 **디버그**로 설정되어 있는지 확인해야 합니다. 디버그 구성은 중단점, 데이터 시각화 도우미 사용, 호출 스택 보기 등 디버깅을 지원하는 유용한 도구 집합을 제공합니다.

![디버그 구성](media/debugging-image_0.png)

## <a name="setting-a-breakpoint"></a>중단점 설정

IDE에서 중단점을 설정하려면 편집기의 여백 영역에서 중단하려는 코드의 줄 번호 옆을 클릭합니다.

![여백에 중단점 설정](media/debugging-image0.png)

**중단점 패드**로 이동하면 코드에 설정된 모든 중단점을 볼 수 있습니다.

![중단점 목록](media/debugging-image0a.png)

## <a name="start-debugging"></a>디버깅 시작

디버깅을 시작하려면 IDE에서 대상 디바이스 또는 유사 디바이스/에뮬레이터를 선택합니다.

![대상 디바이스 선택](media/debugging-image1.png)

그런 다음 **재생** 단추 또는 **Cmd+return**을 눌러 애플리케이션을 배포합니다. 중단점을 적중하면 코드가 노란색으로 강조 표시됩니다.

![중단점이 적중되었음을 보여 주는 강조 표시](media/debugging-image2.png)

이 시점에서 개체 값을 검사하는 데 사용되는 도구 등의 디버깅 도구를 사용하여 코드에서 발생하는 상황에 대한 자세한 정보를 얻을 수 있습니다.

![디버그 시각화](media/debugging-image3.png)

## <a name="conditional-breakpoints"></a>조건부 중단점

중단점이 발생해야 하는 상황을 지정하는 규칙을 설정할 수도 있습니다. 이를 *조건부 중단점* 추가라고 합니다. 조건부 중단점을 설정하려면 **중단점 속성 창**에 액세스합니다. 다음 두 가지 방법으로 액세스할 수 있습니다.

* 새 조건부 중단점을 추가하려면 편집기 여백에서 중단점을 설정하려는 코드의 줄 번호 왼쪽을 마우스 오른쪽 단추로 클릭하고 새 중단점을 선택합니다.

 ![중단점 상황에 맞는 메뉴](media/debugging-image4.png)

* 기존 중단점에 조건을 추가하려면 중단점을 마우스 오른쪽 단추로 클릭하고 **중단점 속성**을 선택하거나 **중단점 패드**에서 아래 그림에 표시된 중단점 편집 단추를 선택합니다.

 ![중단점 패드에서 기존 중단점 편집](media/debugging-image5.png)

그런 다음 중단점이 발생할 조건을 입력할 수 있습니다.

 ![중단점 조건 편집](media/debugging-image6.png)

## <a name="stepping-through-code"></a>단계별 코드 실행

중단점에 도달하면 디버그 도구를 사용하여 프로그램 실행을 제어할 수 있습니다. Mac용 Visual Studio에서 코드를 실행하고 단계별로 실행할 수 있는 단추 4개를 표시합니다. Mac용 Visual Studio에서는 다음과 같이 표시됩니다.

 ![코드를 단계별로 실행하는 단추](media/debugging-image7.png)

네 단추는 다음과 같습니다.

* **재생** - 다음 중단점까지 코드 실행을 시작합니다.
* **프로시저 단위 실행** - 다음 코드 줄을 실행합니다. 다음 줄이 함수 호출인 경우 프로시저 단위 실행은 함수를 실행하고, 함수 *뒤*의 다음 코드 줄에서 중지합니다.
* **한 단계씩 코드 실행** - 다음 코드 줄을 실행합니다. 다음 줄이 함수 호출인 경우 한 단계씩 코드 실행은 함수의 첫 번째 줄에서 중지되며, 함수 디버깅을 줄 단위로 계속할 수 있도록 합니다. 다음 줄이 함수가 아닌 경우 프로시저 단위 실행과 동일하게 동작합니다.
* **프로시저 나가기** - 현재 함수가 호출된 줄로 돌아갑니다.

## <a name="debugging-monos-class-libraries"></a>Mono의 클래스 라이브러리 디버깅

Xamarin 제품은 Mono 클래스 라이브러리에 대한 소스 코드와 함께 제공되며, 이 소스 코드를 사용하여 디버거에서 한 단계씩 실행하면서 코드가 어떻게 동작하는지 검사할 수 있습니다.

이 기능은 디버그 중에 추가 메모리를 사용하므로 기본적으로 꺼져 있습니다.

이 기능을 사용하려면 **Mac용 Visual Studio > 기본 설정 > 디버거**로 이동한 다음, 아래 그림과 같이 “**프로젝트 코드만 디버깅합니다. 프레임워크 코드는 한 단계씩 실행하지 마세요.** ” 옵션이 **선택 취소**되어 있어야 합니다.

![프레임워크 코드는 한 단계씩 실행하지 마세요 옵션](media/debugging-image8.png)

## <a name="see-also"></a>참고 항목

- [Visual Studio의 디버깅(Windows에서)](/visualstudio/debugger/)