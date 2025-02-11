---
title: XAML 핫 다시 로드를 사용 하 여 XAML 작성 및 디버그
description: Xaml 핫 다시 로드 또는 XAML 편집 하며 계속 하기를 사용 하 여 앱을 실행 하는 동안 XAML 코드를 변경할 수 있습니다.
ms.date: 08/05/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0acacac883153990861385c96eeb3379c464f97f
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870996"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>Visual Studio에서 XAML 핫 다시 로드를 사용 하 여 실행 중인 XAML 코드 작성 및 디버그

XAML 핫 다시 로드를 사용 하면 앱이 실행 되는 동안 XAML 코드를 변경할 수 있으므로 WPF 또는 UWP 앱 UI (사용자 인터페이스)를 빌드할 수 있습니다. 핫 다시 로드는 Visual Studio와 Blend for Visual Studio에서 모두 사용할 수 있습니다. 이 기능을 사용 하면 실행 중인 응용 프로그램의 데이터 컨텍스트, 인증 상태 및 디자인 타임 동안 시뮬레이션 하기 어려운 기타 실제 복잡성의 이점을 활용 하 여 XAML 코드를 점진적으로 빌드 및 테스트할 수 있습니다.

XAML 핫 다시 로드는 다음과 같은 시나리오에서 특히 유용 합니다.

* 응용 프로그램이 디버그 모드에서 시작 된 후 XAML 코드에서 발견 된 UI 문제를 수정 합니다.

* 응용 프로그램의 런타임 컨텍스트를 활용 하면서 개발 중인 앱에 대 한 새 UI 구성 요소를 구축 합니다.

|지원 되는 응용 프로그램 유형|운영 체제 및 도구|
|-|-|-|
|WPF(Windows Presentation Foundation) |.NET Framework 4.6+</br>Windows 7 이상 |
|UWP (유니버설 Windows 앱)|Windows 10 이상, [windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> Visual Studio XAML 핫 다시 로드는 현재 Visual Studio에서 응용 프로그램을 실행 하거나 디버거가 연결 된 Blend for Visual Studio (**F5** 또는 **디버깅 시작**) 하는 경우에만 지원 됩니다. [프로세스에 연결을](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)사용 하 여이 환경을 사용 하도록 설정할 수 없습니다.

## <a name="known-limitations"></a>알려진 제한 사항

다음은 XAML 핫 다시 로드의 알려진 제한 사항입니다. 실행 되는 제한 사항을 해결 하려면 디버거를 중지 한 후 작업을 완료 합니다.

|제한 사항|WPF|UWP|참고|
|-|-|-|-|
|앱이 실행 되는 동안 컨트롤에 이벤트 연결|지원되지 않음|지원되지 않음|자세한 내용은 오류: *이벤트 실패 확인*|
|리소스 사전에 앱의 페이지/창 또는 *app.xaml* 과 같은 리소스 개체 만들기|지원되지 않음|지원됨|예제:를 `StaticResource`으로 `SolidColorBrush` 사용할 리소스 사전에 추가 합니다.</br>참고: 정적 리소스, 스타일 변환기 및 리소스 사전에 작성 된 기타 요소는 XAML 핫 다시 로드를 사용 하는 동안 적용/사용할 수 있습니다. 리소스 만들기만 지원 되지 않습니다.</br> 리소스 사전 `Source` 속성을 변경 합니다.|
|앱이 실행 되는 동안 프로젝트에 새 컨트롤, 클래스, 창 또는 기타 파일 추가|지원되지 않음|지원되지 않음|없음|
|NuGet 패키지 관리 (패키지 추가/제거/업데이트)|지원되지 않음|지원되지 않음|없음|
|{X:Bind} 태그 확장을 사용 하는 데이터 바인딩 변경|N/A|Visual Studio 2019 이상 버전에서 지원 됨|Visual Studio 2017 또는 이전 버전에서는 지원 되지 않음|

## <a name="error-messages"></a>오류 메시지

XAML 핫 다시 로드를 사용 하는 동안 다음 오류가 발생할 수 있습니다.

|오류 메시지|Description|
|-|-|
|이벤트 실패 확인|오류는 응용 프로그램이 실행 되는 동안 지원 되지 않는 컨트롤 중 하나에 이벤트를 연결 하려고 시도 하 고 있음을 나타냅니다.|
|XAML 편집하며 계속하기에서 업데이트할 요소를 찾지 못했습니다.|앱에서 핫 다시 로드를 업데이트할 수 없는 XAML을 편집 하는 경우 오류가 발생 합니다.</br> 이러한 오류는 실행 중인 응용 프로그램을 사용 하 여 XAML이 사용 된 뷰로 이동 하 여 해결할 수 있습니다.</br> 경우에 따라이 오류는 디버깅 세션을 다시 시작할 때까지 특정 변경 내용을 적용할 수 없음을 의미 합니다. |
|디버깅 세션 동안에는 이러한 변경을 할 수 없습니다.|오류는 XAML 핫 다시 로드에서 시도 중인 변경을 지원 하지 않음을 나타냅니다. 디버깅 세션을 중지 하 고, 변경 하 고 나 서, 디버깅 세션을 다시 시작 합니다.|
