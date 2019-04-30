---
title: 작성 하 고 XAML 핫 다시 로드를 사용 하 여 XAML 디버그
description: 활성 XAML을 다시 로드 또는 XAML 편집 하며 계속 하기, 앱을 실행 하는 동안 XAML 코드를 변경할 수 있습니다.
ms.custom: ''
ms.date: 02/28/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a002c3876eecf0f31a8d104fa235b1208af90699
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929138"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>작성 하 고 Visual Studio에서 XAML 핫 다시 로드를 사용 하 여 실행 중인 XAML 코드를 디버그 합니다.

활성 visual Studio XAML 앱이 실행 되는 동안 XAML 코드를 변경할 수 있도록 하 여 WPF 또는 UWP 앱 UI를 빌드하는 데 도움이 됩니다. 다시 로드 합니다. 이 기능을 통해 증분 방식으로 빌드 및 실행 중인 앱의 데이터 컨텍스트, 인증 상태 및 디자인 타임 동안 시뮬레이션 하기 어려운 다른 실제 복잡성의 혜택을 사용 하 여 XAML 코드를 테스트할 수 있습니다.

XAML 핫 다시 로드 이러한 시나리오에서 특히 유용 합니다.

* XAML 코드를 디버그 모드에서 앱을 시작한 후에 UI 문제를 해결 합니다.

* 앱에 대 한 새 UI 구성 요소를 빌드하는 앱의 런타임 컨텍스트를 활용 하는 동안 개발입니다.

|지원 되는 응용 프로그램 유형|운영 체제 및 도구|
|-|-|-|
|WPF(Windows Presentation Foundation) |.NET Framework 4.6+</br>Windows 7 이상 |
|유니버설 Windows 앱 (UWP)|Windows 10 이상에서 사용 하 여 합니다 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> Visual Studio XAML 핫 다시 로드는 현재 Visual Studio에서 디버거가 연결 된 응용 프로그램을 실행 하는 경우에 지원 (**F5** 하거나 **디버깅 시작**). 이 환경을 사용 하 여 사용할 수 없습니다 *프로세스에 연결*합니다.

## <a name="known-limitations"></a>알려진 제한 사항

다음은 알려진 XAML의 제한 사항 핫 다시 로드 합니다. 실행 하는 모든 제한을 해결 하려면 디버거를 중지 하 고 작업을 완료 합니다.

|제한|WPF|UWP|노트|
|-|-|-|-|
|앱이 실행 되는 동안 컨트롤에 이벤트에 연결|지원되지 않음|지원 안 함|오류를 참조 하세요. *이벤트 확인 실패*|
|앱의 페이지/창에서 같은 리소스 사전에서 리소스 개체를 만들 또는 *App.xaml*|지원되지 않음|지원됨|예: 추가 된 ```SolidColorBrush``` 사용에 대 한 리소스 사전에는 ```StaticResource```.</br>참고: 정적 리소스, 스타일 변환기 및 리소스 사전에 기록 되는 다른 요소 수 적용 하 고 사용 XAML 핫 다시 로드를 사용 하는 동안. 리소스의 생성만 지원 되지 않습니다.</br> 리소스 사전을 변경 ```Source``` 속성입니다.| 
|앱이 실행 되는 동안 새로운 컨트롤, 클래스, windows 또는 기타 파일 프로젝트에 추가|지원되지 않음|지원되지 않음|없음|
|NuGet 패키지 관리 (추가/제거/업데이트 패키지)|지원되지 않음|지원되지 않음|없음|
|{X:bind} 태그 확장을 사용 하는 바인딩 데이터 변경|N/A|Visual Studio 2019 및 이상 버전에서 지원|Visual Studio 2018 또는 이전 버전에서 지원 되지 않습니다.|

## <a name="error-messages"></a>오류 메시지

XAML 핫 다시 로드를 사용 하는 동안 다음 오류가에서 가져올 수 있습니다.

|오류 메시지|설명|
|-|-|-|
|이벤트 확인 실패|오류, 응용 프로그램을 실행 하는 동안 지원 되지 않는 컨트롤 중 하나에 이벤트를 연결 하려는 것을 나타냅니다.|
|XAML 편집하며 계속하기에서 업데이트할 요소를 찾지 못했습니다.|오류가 발생을 편집할 때 핫 다시 로드 하는 XAML 앱에서 업데이트할 수 없습니다.</br> 이 오류를 사용 하 여 실행 중인 앱을 보기를 탐색 하는 XAML을 사용 하는 경우에 따라 해결할 수 있습니다.</br> 경우에 따라이 오류는 디버깅 세션을 다시 시작 될 때까지 특정 변경 내용을 적용할 수 없습니다를 의미 합니다. |
|디버깅 세션 동안에는 이러한 변경을 할 수 없습니다.|오류 하려는 변경 XAML 핫 다시 로드 하 여 지원 되지 않습니다 나타냅니다. 디버깅 세션을 중지 하 고, 변경한 다음 디버깅 세션을 다시 시작 합니다.|