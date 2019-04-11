---
title: Visual Studio extender에 대 한 모니터별 인식을 지원
titleSuffix: ''
description: 당 모니터-인식 Visual Studio 2019에서 사용할 수 있는 새 extender 지원에 알아봅니다.
ms.date: 04/09/2019
helpviewer_keywords:
- Visual Studio, PMA, per-monitor-awareness, extenders, Windows Forms
- Per-Monitor Awareness support for extenders
ms.assetid: ''
author: rub8n
ms.author: rurios
manager: anthc
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: reference
ms.workload:
- multiple
ms.openlocfilehash: 42de73a29e053066c0fbeca72ca3511b58b2fa7e
ms.sourcegitcommit: 0a2fdc23faee77187e10a1c19665ba5a1ac68e72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477693"
---
# <a name="per-monitor-awareness-support-for-visual-studio-extenders"></a>Visual Studio extender에 대 한 모니터별 인식을 지원

Visual Studio 2019 이전 버전에는 해당 DPI 인식 컨텍스트는 모니터별 DPI 인식 (PMA) 보다는 인식 시스템 설정 했습니다. 인식 발생 하는 시스템에서 실행 되는 성능이 저하 된 시각적 효과 (예: 흐리게 글꼴 또는 아이콘)에서 Visual Studio가 다른 배율 인수를 사용 하 여 모니터에서 렌더링 해야 할 때마다 또는 디스플레이 구성 (예: 다른 컴퓨터에 원격으로 Windows 확장)입니다.

Visual Studio 2019 DPI 인식 컨텍스트는 정의 하는 일반 시스템 구성을 대신 모니터별 호스팅되는 디스플레이의 구성에 따라 렌더링에 Visual Studio 인식 되는, 허용으로 설정 합니다. 궁극적으로 PMA 지원을 구현 하는 화면 영역에 대 한 생생한 UI로 변환 합니다.

참조를 [Windows에서 높은 DPI 데스크톱 응용 프로그램 개발](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) 설명서 전체 시나리오에 대 한 자세한 내용은이 문서에서 설명 합니다.

## <a name="quickstart"></a>빠른 시작
- Visual Studio PMA 모드에서 실행 중인지 확인 (참조 **PMA 사용**)

- 여러 일반적인 시나리오에 확장 작동을 올바르게 확인할 (참조 **PMA 문제에 대 한 확장을 테스트**)

- 문제를 찾을 경우 있습니다 됩니다 필요 새 PMA nugget 패키지를 추가 하려면 진단 및 전략 및이 문서에 설명 된 권장 사항을 사용 하 여 문제 해결

## <a name="enabling-pma"></a>PMA를 사용 하도록 설정
PMA Visual studio에서를 사용 하려면 다음 요구 사항을 충족 해야 합니다.
1)  Windows 10 2018 년 4 월 업데이트 (v1803 RS4) 이상
2)  .NET framework 4.8 RTM 이상 (현재 독립 실행형 미리 보기 또는 최근와 함께 번들으로 제공 Windows Insider 빌드)
3)  사용 하 여 visual Studio 2019 합니다 ["다른 픽셀 밀도 사용 하 여 화면에 대 한 최적화 렌더링"](https://docs.microsoft.com/visualstudio/ide/reference/general-environment-options-dialog-box?view=vs-2019) 옵션이 사용 하도록 설정

이러한 요구 사항이 충족 되 면 Visual Studio 프로세스 전체에서 PMA를 자동으로 사용 됩니다.

## <a name="testing-your-extensions-for-pma-issues"></a>PMA 문제에 대 한 확장을 테스트

Visual Studio WPF, Windows Forms, Win32, 및 HTML/JS UI 프레임 워크를 공식적으로 지원합니다. Visual Studio PMA 모드로 설정 됩니다, 다른 UI 스택 다르게 동작 합니다. 따라서 UI 프레임 워크에 관계 없이 모든 UI가 PMA 호환 되도록 테스트 통과 수행 되는 것이 좋습니다.

UI 프레임 워크에 관계 없이 확장 프로그램에서는 다음과 같은 일반적인 시나리오를 확인 하는 것이 좋습니다.

1. 응용 프로그램은 실행 * 하는 동안 단일 모니터 환경의 배율 인수를 변경 합니다.
    - 이 시나리오를 통해 UI 동적 Windows DPI 변경에 응답 하는지 테스트 합니다.

2. 연결된 모니터를 주 복제본과 연결된 된 모니터에 설정 되어 있는 랩톱 응용 프로그램이 실행 되는 동안 기본에 비해 다른 배율 인수를 도킹 하 고 도킹 합니다.
    - 이 시나리오를 통해 동적 표시 처리 뿐만 아니라 DPI가 변경 되 고 추가 또는 제거 UI를 표시할 응답 하는지 테스트 합니다.

3. 다른 배율 인수를 사용 하 여 여러 모니터를 필요 하 고 응용 프로그램 간에 이동 합니다.
    - 이 시나리오를 통해 UI 디스플레이 DPI 변경에 응답 하는지 테스트 합니다.
    
4. 로컬 및 원격 컴퓨터에 기본 모니터에 대 한 다른 배율 인수 하는 경우 컴퓨터에 원격입니다.
    - 이 시나리오를 통해 UI 동적 Windows DPI 변경에 응답 하는지 테스트 합니다.

UI 데 문제가 있을 수 있는지 여부에 대 한 적절 한 예비 테스트는 코드를 하나 사용 여부는 *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper* 또는 *Microsoft.VisualStudio.PlatformUI.DpiHelper* 클래스입니다. 이러한 이전 DpiHelper 클래스에만 시스템 DPI를 인식 지원 프로세스가 PMA 되 면 제대로 작동 하지 않을 항상 있습니다.

이러한 DpiHelpers의 일반적인 사용은 같이 표시 됩니다.

```cs
Point screenTopRight = logicalBounds.TopRight.LogicalToDeviceUnits();

POINT screenIntTopRight = new POINT
{
    x = (int)screenTopRIght.X,
    y = (int)screenTopRIght.Y
}

IntPtr monitor = NativeMethods.MonitorFromPoint(screenIntTopRight, NativeMethods.Monitor_DEFAULTTONEARST);
```

이전 예제에서는 창의 논리적 범위를 나타내는 사각형 MonitorFromPoint 다시 정확한 모니터 포인터를 반환 하기 위해 장치 좌표를 필요로 하는 기본 메서드에 전달할 수 있도록 장치 단위 변환 됩니다.

### <a name="classes-of-issues"></a>문제의 클래스

PMA for Visual Studio를 사용 하는 경우 UI 몇 가지 일반적인 방법으로 문제를 복제할 수 있습니다. 대부분 경우 항상 그렇지는 않지만 이러한 문제의 발생할 수 있습니다 Visual Studios 지원 되는 UI 프레임 워크 중 하나. 또한도 경우 UI 부분에에서 호스팅되고 시나리오를 확장 하는 혼합 모드 DPI 이러한 문제를 발생할 수 있습니다 (Windows를 참조 하세요 [설명서](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows) 자세한). 

#### <a name="win32-window-creation"></a>Win32 창 만들기
Windows CreateWindow() 또는 CreateWindowEx()를 만들 때 일반적인 패턴은 좌표 0, 0 시 창 (위쪽/왼쪽 모퉁이 기본 디스플레이의)을 만들려면 다음 이동의 최종 위치에. 그러나 이렇게 DPI를 트리거할 수 있는 창을 하면 메시지 또는 다른 UI 메시지 또는 이벤트로 다시 트리거할 수 있습니다 및 결과적으로 원치 않는 동작이 나 렌더링 하는 경우 변경 합니다.

#### <a name="wpf-element-placement"></a>WPF 요소 배치
이전 Microsoft.VisualStudio.Utilities.Dpi.DpiHelper를 사용 하 여 WPF 요소를 이동할 때 왼쪽 위 좌표 비기본 DPI 경우에서 요소가 때마다 올바르게 계산 되지 않을 수 있습니다.

#### <a name="serialization-of-ui-element-sizes-or-positions"></a>UI 요소 크기 또는 위치의 serialization
UI 크기 또는 위치에 저장 된 것 보다는 서로 다른 DPI 컨텍스트에서 복원 되 면 때마다 수 배치 하 고 올바르게 크기 조정 합니다. 창의 논리적 경계 MonitorFromPoint 다시 정확한 모니터 포인터를 반환 하기 위해 장치 좌표를 필요로 하는 Win32 메서드에 전달할 수 있도록 장치 단위 변환 됩니다 때문에 발생 합니다.

#### <a name="incorrect-scaling"></a>잘못 된 크기 조정
기본 DPI에서 만드는 UI 요소는 있지만 다른 dpi 디스플레이에 이동 하는 경우 크기를 변경 하지는 즉, 해당 콘텐츠 결국 너무 크거나 너무 작아서 올바르게 확장 됩니다.

#### <a name="incorrect-bounding"></a>잘못 된 경계
하지만 마찬가지로, 크기 조정 문제에 UI 요소는 계산 올바르게 해당 기본 DPI 컨텍스트를 해당 범위를 보조로 이동 하면 새 범위를 올바르게 계산 되지 않습니다는. 따라서 콘텐츠 창이 끝납니다 너무 작거나 너무 큰 되 고 빈 공간 또는 클리핑은 호스팅 UI에 비해.

#### <a name="drag--drop"></a>끌어서 놓기
때마다 끌어서 놓기, 혼합 모드 DPI 시나리오 (예: 다른 UI 요소 기본 및 보조 DPI 컨텍스트에서 렌더링) 내에서 좌표 수 수 빈번 하 게, 잘못 된 등록 최종 드롭 위치 끝에서 발생 합니다.

#### <a name="out-of-process-ui"></a>Out-of-process-UI
일부 UI out-of-process-만들어지고 이전 렌더링 문제가 발생할 수 있습니다 만드는 외부 프로세스가 Visual Studio 보다 다른 DPI 인식 모드인 경우.

#### <a name="windows-forms-controls-images-or-windows-not-displaying"></a>Windows Forms 컨트롤, 이미지 또는 표시 되지 않는 windows
이 문제에 대 한 주요 원인 중 하나는 컨트롤 또는 다른 DpiAwarenessContext 창으로 하나의 DpiAwarenessContext 창 부모 재지정 하려는 개발자에 게입니다. 

다음 그림 동작을 호스트 하는 스레드 명시적으로 변경 하지 않으면 windows에서 부모로 지정에서 현재 Windows 운영 체제 제한을 보여 줍니다.

![올바른 부모/자식 관리 동작의 스크린샷](../../extensibility/ux-guidelines/media/PMA-parenting-behavior.PNG)

결과적으로, 지원 되지 않는 모드 간의 부모-자식 관계를 설정 하는 경우, 실패 및 예상 대로 컨트롤이 나 창 렌더링 되지 않을 수 있습니다.

### <a name="diagnosing-issues"></a>문제 진단
가지 PMA 관련 문제를 식별 하는 경우를 고려해 야 할 여러 요인이 있습니다. 

1. UI 또는 예상 되는 API는 논리 또는 장치 값입니다.
    - WPF UI와 Api를 일반적으로 사용 하 여 논리 값 (항상 그렇지는 않지만)
    - Win32 UI와 Api를 일반적으로 장치 값 사용

2. 값에서 생성 되는 위치
    - 값을 다른 UI 또는 API에서 받은 전달 장치 또는 논리 값입니다.
    - 여러 소스에서 값을 수신 하는 경우 모두 사용 하 여/예상 않는 동일한 형식의 값 또는 변환 필요가 혼합 및 일치 수 있습니까?

3. 사용 중인 UI 상수 및에 어떤 형식?

4. 스레드는 값에 대 한 올바른 DPI 컨텍스트에서 발생?
    - 하지만 CLMM 수 있도록 변경 내용을 적절 한 상황에서 일반적으로 코드 경로 입력 해야, 잘못 된 DPI 컨텍스트에서 주 메시지 루프 또는 이벤트 흐름 외부에서 수행 하는 작업 실행 될 수 있습니다 합니다.

5. 값은 DPI 컨텍스트 경계를 넘나들 수행?
    - 끌어서 놓기 좌표 DPI 컨텍스트를 넘을 수 있는 일반적인 현상입니다. 창 오른쪽 작업을 수행 하려고 시도 하지만 경우에 따라 호스트 UI의 일치 하는 컨텍스트 경계 되도록 변환 작업을 수행 해야 할 수 있습니다.

### <a name="pma-nugget-package"></a>PMA Nugget 패키지
새 DpiAwarness 라이브러리 Microsoft.VisualStudio.DpiAwareness NuGet 패키지에서 찾을 수 있습니다.

### <a name="recommended-tools"></a>권장된 도구
다음 도구는 Visual Studio에서 지 원하는 다른 UI 스택의 일부 PMA 관련 문제를 디버그 하는 데 도움이 됩니다.

#### <a name="snoop"></a>스 눕
Snoop는 XAML 디버깅 도구에 기본 제공 Visual Studio XAML 도구 없는 몇 가지 추가 기능입니다. 또한 Snoop 적극적으로 보기 및 해당 WPF UI를 조정 하는 일을 할 수 있는 Visual Studio 디버그 필요가 없습니다. 논리적 배치 좌표나 크기 범위 유효성 검사에 대 한 Snoop PMA 문제를 진단 하는 데 유용할 수 있습니다 하는 두 가지 주요 방법 이며 유효성 검사에 대 한 UI의 오른쪽 DPI입니다.
 
#### <a name="visual-studio-xaml-tools"></a>Visual Studio XAML 도구
Snoop와 같은 Visual Studio에서 XAML 도구 도움이 PMA 문제를 진단 합니다. 가능성이 높은 원인 발견 되 면 중단점을 설정할 수 있으며 라이브 시각적 트리 창 뿐만 아니라 디버그 windows를 사용 하 여 UI 범위 및 현재 DPI를 검사할 수 있습니다.

## <a name="strategies-for-fixing-pma-issues"></a>PMA 문제를 해결 하기 위한 전략

### <a name="replacing-dpihelper-calls"></a>대체 DpiHelper 호출
대부분의 경우에서 PMA에서 UI 문제를 해결 나눌 수 이전에 관리 코드에 대 한 호출을 대체 합니다. *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper* 하 고 *Microsoft.VisualStudio.PlatformUI.DpiHelper* 클래스를 새를 호출 하 여 *Microsoft.VisualStudio.Utilities.DpiAwareness* 도우미 클래스입니다. 

네이티브 코드에 대 한 것을 수반 이전에 대 한 대체 호출 *VsUI::CDpiHelper* 새 호출을 사용 하 여 클래스 *VsUI::CDpiAwareness* 클래스입니다. 새로운 DpiAwareness 및 CDpiAwareness 클래스 DpiHelper 클래스 추가 입력된 매개 변수를 필요 하지만 동일한 변환 도우미를 제공 합니다: 변환 작업에 대 한 참조로 사용할 UI 요소입니다. 

관리 되는 DpiAwareness 클래스는 네이티브 CDpiAwareness 클래스 제품 HWND 및 HMONITOR 도우미를 하는 동안 WPF 시각적 개체, Windows Forms 컨트롤 및 Win32 Hwnd HMONITORs (둘 다 IntPtrs의 형태로)에 대 한 도우미를 제공합니다.

### <a name="windows-forms-dialogs-windows-or-controls-displayed-in-the-wrong-dpiawarenesscontext"></a>Windows Forms 대화 상자, windows 또는 잘못 된 DpiAwarenessContext 표시 컨트롤
다른 DpiAwarenessContext (때문에 windows 기본 동작)를 사용 하 여 windows의 성공적인 부모 지정 후에 여전히 나타날 다른 DpiAwarenessContext windows 다르게 크기 조정에 따른 문제를 확장 합니다. 결과적으로, 사용자 UI에서 맞춤/흐린 텍스트 또는 이미지 문제 표시 될 수 있습니다.

솔루션 응용 프로그램에서 모든 windows 및 컨트롤에 대 한 올바른 DpiAwarenessContext 범위를 설정 하는 것입니다.

### <a name="tlmm-dialogs"></a>TLMM 대화 상자
모달 대화 상자와 같은 최상위 창을 만들면, 것이 중요 스레드가 생성 되 고 HWND 전에 올바른 상태 인지 확인 합니다. 스레드가 네이티브에서 CDpiScope 도우미를 사용 하는 시스템 인식 하 여 모드로 전환할 수 있습니다 또는 DpiAwareness.EnterDpiScope 도우미를 관리 합니다. (TLMM 일반적으로 사용할 비 WPF 대화 상자/windows에서.)

### <a name="child-level-mixed-mode-clmm"></a>자식 수준 혼합된 모드 (CLMM)

기본적으로 자식 창의 부모 같은 DPI 인식 모드를 받습니다. 그러나 SetThreadDpiHostingBehavior를 사용 하 여이 재정의할 수 및 자식 창을 해당 부모 또는 호스트 보다 다양 한 크기 조정 모드로 실행 합니다.


#### <a name="clmm-issues"></a>CLMM 문제
대부분의 기본 메시징 루프 또는 이벤트 체인의 일부로 발생 하는 UI 계산 작업은 적절 한 DPI 상황에서 이미 실행 되어야 합니다. 그러나 경우 좌표 또는 크기 조정 계산 작업을 마쳤으면 이러한 기본 워크플로 외부 (예: 유휴 시간 작업을 하는 동안 또는 UI 스레드에서 다음 DPI 컨텍스트에 올바르지 않을 UI misplacement을 선행 공백 또는 잘못 문제 크기 조정 합니다. Ui 스레드를 올바른 상태로 배치 작업 일반적으로 문제를 해결을 합니다.
 
#### <a name="opting-out-of-clmm"></a>CLMM 옵트아웃
비 WPF 도구 창을 완벽 하 게 지원 PMA 마이그레이션 중인 경우 CLMM 옵트아웃 해야 합니다. 이렇게 하려면 새 인터페이스를 구현 해야 합니다. IVsDpiAware 합니다.

C#: 
```cs
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
public interface IVsDpiAeware
{
    [ComAliasName("Microsoft.VisualStudio.Shell.Interop.VSDPIMode")]
    uint Mode {get;}
}
```
 
C++:
```cplusplus
IVsDpiAware : public IUnknown
{
    public:
        HRRESULT STDMETHODCALLTYPE get_Mode(__RCP__out VSDPIMODE *dwMode);
};
```
 

파생 되는 동일한 클래스에는이 인터페이스를 구현 하는 것이 좋습니다 관리 되는 언어에 대 한 *Microsoft.VisualStudio.Shell.ToolWindowPane*합니다. 에 대 한 C++를 구현 하는 동일한 클래스에는이 인터페이스를 구현 하는 것이 좋습니다 *IVsWindowPane* vsshell.h에서.

인터페이스에서 모드 속성에 의해 반환 되는 __VSDPIMODE (및 관리에서 uint로 캐스팅):

```cs
enum __VSDPIMODE
    {
        VSDM_Unaware    = 0x01,
        VSDM_System     = 0x02,
        VSDM_PerMonitor = 0x03,
    }
```

- 도구 창을 96DPI 처리 해야 하는 경우를 인식 하지 못하는 의미 Windows 모든 다른 Dpi에 대 한 크기 조정을 처리 합니다. 약간 흐리게 표시 되는 내용에 발생 합니다.
- 도구 창을 주에 대 한 DPI를 처리 해야 하는 시스템 의미 DPI를 표시 합니다. 일치 하는 DPI 사용 하 여 모든 디스플레이 관하여 알게 보이지만 DPI 다릅니다 또는 세션 중에 변경 하는 경우 Windows에서 크기 조정을 처리 하는 하 고 약간 흐리게 표시 됩니다.
- PerMonitor 모든 디스플레이에 모든 Dpi를 처리 해야 하는 도구 창 및 DPI가 변경 될 때마다 의미 합니다.

**참고**: Visual Studio는 PerMonitor 열거형 값을 DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2 Windows 값으로 변환 하므로 PerMonitorV2 인식을 지원 합니다.

## <a name="known-issues"></a>알려진 문제

### <a name="windows-forms"></a>Windows Forms

을 최적화 하기 위해 새로운 혼합 모드 시나리오에 대 한 Windows Forms 만드는 방법을 변경 컨트롤 및 windows 때마다 해당 부모 명시적으로 설정 되지 않았습니다. 이전에 명시적 부모 없이 컨트롤을 내부 "파킹 창을 사용" 임시 부모 컨트롤 또는 생성 되는 창으로 합니다. 

"파킹 창" 응용 프로그램에서 실행 중인 프로세스에서 해당 DpiAwarenessContext를 가져옵니다. 파킹 창으로 동일한 DpiAwarenessContext 상속 컨트롤과 다음 부모를 재지정할 수 원래/예상 부모 응용 프로그램 개발자.  이 컨트롤에 사용 하려는 부모 만들어지는 컨트롤로 동일한 DpiAwarenessContext 없는 경우 작동 하지 않습니다.

.NET 4.8을 기준으로 부모 컨트롤 또는 창에서 명시적으로 설정 되어 있지 않으면 Windows Forms 컨트롤이 나 창 만들기 요청 스레드의 DpiAwarenessContext 일치 하는 파킹 창에 대 한 쿼리를 임시 부모로 사용 합니다. 즉, 생성 될 때 컨트롤 의도 한 DpiAwarenessContext를 사용 하 여 생성 이제 됩니다. 컨트롤이 나 창 다음 예상 부모 응용 프로그램 개발자가 레코드가 됩니다.
