---
title: VSTO 추가 기능의 성능 향상
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2add0dfced6a3b8e8263dafe133ee3a2f86637f5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63420932"
---
# <a name="improve-the-performance-of-a-vsto-add-in"></a>VSTO 추가 기능에 성능을 향상합니다
  Office 애플리케이션용으로 만드는 VSTO 추가 기능을 최적화하여 신속하게 시작하고, 종료하고, 항목을 열고, 다른 작업을 수행할 수 있는 향상된 환경을 사용자에게 제공할 수 있습니다. VSTO 추가 기능이 Outlook용인 경우 낮은 성능 때문에 VSTO 추가 기능이 사용하지 않도록 설정될 가능성도 줄일 수 있습니다. 다음 전략을 실행하여 VSTO 추가 기능의 성능을 높일 수 있습니다.

- [요청 시 VSTO 추가 기능 로드](#Load)

- [Windows Installer를 사용하여 Office 솔루션 게시](#Publish)

- [리본 리플렉션 우회](#Bypass)합니다.

- [별도의 실행 스레드에서 비용이 많이 드는 작업 수행](#Perform)

  최적화는 Outlook VSTO 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [VSTO 추가 기능 사용을 유지 하는 성능 조건을](http://go.microsoft.com/fwlink/?LinkID=266503)합니다.

## <a name="Load"></a> 요청 시 VSTO 추가 기능 로드
 다음과 같은 경우에만 로드되도록 VSTO 추가 기능을 구성할 수 있습니다.

- VSTO 추가 기능이 설치된 후 사용자가 애플리케이션을 처음으로 시작하는 경우

- 이후에 애플리케이션을 시작한 후 사용자가 VSTO 추가 기능과 처음으로 상호 작용하는 경우

  예를 들어, VSTO 추가 기능에 채울 수 있습니다 워크시트 데이터를 레이블이 지정 된 사용자 지정 단추를 선택 하면 **내 데이터 가져오기**합니다. 응용 프로그램이 VSTO 추가 기능에 적어도 한 번 로드 해야 되도록 합니다 **내 데이터 가져오기** 단추가 리본에 나타날 수 있습니다. 그러나 VSTO 추가 기능에서 다시 로드 되지 않습니다 사용자가 다음에 응용 프로그램을 시작 하는 경우. VSTO 추가 기능은 사용자가 **내 데이터 가져오기** 단추를 선택할 때만 로드됩니다.

### <a name="to-configure-a-clickonce-solution-to-load-vsto-add-ins-on-demand"></a>요청 시 VSTO 추가 기능을 로드하도록 ClickOnce 솔루션을 구성하려면

1. **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.

2. 메뉴 모음에서 **보기** > **속성 페이지**를 선택합니다.

3. **게시** 탭에서 **옵션** 단추를 선택합니다.

4. **게시 옵션** 대화 상자에서 **Office 설정** 목록 항목을 선택하고 **요청 시 로드** 옵션을 선택한 다음 **확인** 단추를 선택합니다.

### <a name="to-configure-a-windows-installer-solution-to-load-vsto-add-ins-on-demand"></a>요청 시 VSTO 추가 기능을 로드하도록 Windows Installer 솔루션을 구성하려면

1. 레지스트리를 설정 합니다 `LoadBehavior` 항목의 합니다 **_루트_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Add-in ID_** 키를 **0x10**합니다.

     자세한 내용은 [VSTO 추가 기능에 대 한 레지스트리 항목](../vsto/registry-entries-for-vsto-add-ins.md)합니다.

### <a name="to-configure-a-solution-to-load-vsto-add-ins-on-demand-while-you-debug-the-solution"></a>솔루션을 디버그하는 동안 요청 시 VSTO 추가 기능을 로드하도록 솔루션을 구성하려면

1. 설정 하는 스크립트를 만들 합니다 `LoadBehavior` 항목의 합니다 **_루트_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Add-in ID_** 키를 **0x10**합니다.

     다음 코드에서는 이 스크립트의 예제를 보여 줍니다.

    ```cmd/sh
    [HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\MyAddIn]
    "Description"="MyAddIn"
    "FriendlyName"="MyAddIn"
    "LoadBehavior"=dword:00000010
    "Manifest"="c:\\Temp\\MyAddIn\\bin\\Debug\\MyAddIn.vsto|vstolocal"

    ```

2. 스크립트를 사용하여 레지스트리를 업데이트하는 빌드 후 이벤트를 만듭니다.

     다음 코드에서는 빌드 후 이벤트에 추가할 수 있는 명령 문자열의 예를 보여 줍니다.

    ```cmd/sh
    regedit /s "$(SolutionDir)$(SolutionName).reg"

    ```

     빌드 후 이벤트를 만드는 방법에 대 한 정보에 대 한는 C# 프로젝트를 참조 하세요 [방법: 빌드 이벤트 지정 &#40;C&#35;&#41;](../ide/how-to-specify-build-events-csharp.md)합니다.

     Visual Basic 프로젝트에서 빌드 후 이벤트를 만드는 방법에 대 한 자세한 내용은 [방법: 빌드 이벤트 지정 &#40;Visual Basic&#41;](../ide/how-to-specify-build-events-visual-basic.md)합니다.

## <a name="Publish"></a> Windows Installer를 사용 하 여 Office 솔루션 게시
 Windows Installer를 사용 하 여 솔루션을 게시 하는 경우 Visual Studio 2010 Tools for Office 런타임 VSTO 추가 기능을 로드 하는 경우 다음 단계를 무시 합니다.

- 매니페스트 스키마의 유효성 검사

- 자동으로 업데이트 확인

- 배포 매니페스트의 디지털 서명 유효성 검사

  > [!NOTE]
  > 이 방법은 VSTO 추가 기능에 사용자의 컴퓨터에서 안전한 위치에 배포 하는 경우 필요는 없습니다.

  자세한 내용은 [Windows Installer를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-windows-installer.md)합니다.

## <a name="Bypass"></a> 리본 리플렉션 우회
 사용 하 여 솔루션을 빌드하면 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], 사용자가 솔루션을 배포 하는 경우 최신 버전의 Visual Studio 2010 Tools for Office 런타임 설치 되어 있는지 확인 합니다. 해당 런타임의 이전 버전 사용자 지정 리본을 찾기 위해 솔루션 어셈블리를 반영 합니다. 이 프로세스로 인해 VSTO 추가 기능이 더 느리게 로드될 수 있습니다.

 대신 리플렉션을 사용 하 여 리본 메뉴 사용자 지정 확인에서 모든 버전의 Visual Studio 2010 Tools for Office 런타임을 방지할 수 있습니다. 이 전략을 수행 하려면 재정의 `CreateRibbonExtensibility` 메서드와 리본 개체를 명시적으로 반환 합니다. VSTO 추가 기능에 리본 사용자 지정이 없으면 반환 `null` 메서드 내에서.

 다음 예에서는 필드의 값을 기준으로 리본 개체를 반환 합니다.

 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_ribbon_choose_ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_ribbon_choose_ribbon_4/ThisWorkbook.cs#1)]

## <a name="Perform"></a> 별도 실행 스레드에서 비용이 많이 드는 작업 수행
 별도의 스레드에서 시간이 많이 걸리는 작업(예: 장기 실행 작업, 데이터베이스 연결 또는 다른 종류의 네트워크 호출)을 수행하는 것이 좋습니다. 자세한 내용은 [Office의 스레딩 지원](../vsto/threading-support-in-office.md)합니다.

> [!NOTE]
> Office 개체 모델을 호출하는 모든 코드는 주 스레드에서 실행되어야 합니다.

## <a name="see-also"></a>참고 항목

- [요청 시 로드 VSTO 추가 기능](https://blogs.msdn.microsoft.com/andreww/2008/07/14/demand-loading-vsto-add-ins/)
- [Office 추가 기능에서 CLR 지연 로드](https://blogs.msdn.microsoft.com/andreww/2008/04/19/delay-loading-the-clr-in-office-add-ins/)
- [Visual Studio를 사용 하 여 Office 용 VSTO 추가 기능 만들기](create-vsto-add-ins-for-office-by-using-visual-studio.md)
