---
title: '프로파일러 명령줄: 클라이언트 .NET 구성 요소 계측, 시간 데이터 가져오기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b7dcc27b-45c6-4302-9552-6fa5b1e94b56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ff23dd4995be70c9a34c95dbe744961b75de3e0c
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67032908"
---
# <a name="how-to-instrument-a-stand-alone-net-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line"></a>방법: 명령줄에서 독립 실행형 .NET Framework 구성 요소 계측 및 프로파일러를 사용하여 타이밍 데이터 수집
이 항목에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 명령줄 도구를 사용하여 .*exe* 또는 .*dll* 파일과 같은 .NET Framework 구성 요소를 계측하고 자세한 타이밍 데이터를 수집하는 방법을 설명합니다.

> [!NOTE]
> Windows 8 및 Windows Server 2012의 강화된 보안 기능을 위해 Visual Studio 프로파일러가 이러한 플랫폼에서 데이터를 수집하는 방법을 상당히 변경해야 했습니다. 또한 UWP 앱에는 새로운 수집 기술도 필요합니다. [Windows 8 및 Windows Server 2012 애플리케이션의 성능 도구](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하세요.
>
> 프로파일링 도구에 대한 경로를 가져오려면 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하세요. 64비트 컴퓨터에서는 도구의 64비트 및 32비트 버전을 둘 다 사용할 수 있습니다. 프로파일러 명령줄 도구를 사용하려면 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.
>
> 프로파일링 실행에 계층 상호 작용 데이터를 추가하려면 명령줄 프로파일링 도구를 사용해서 특정 절차를 수행해야 합니다. [계층 상호 작용 데이터를 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)을 참조합니다.

 계측 방법을 사용하여 .NET Framework 구성 요소에서 자세한 타이밍 데이터를 수집하려면 [VSInstr.exe](../profiling/vsinstr.md) 도구를 사용하여 구성 요소의 계측된 버전을 생성하고 [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 도구를 사용하여 프로파일링 환경 변수를 초기화합니다. 그런 다음 프로파일러를 시작합니다.

 계측된 구성 요소가 실행되면 자동으로 타이밍 데이터가 데이터 파일로 수집됩니다. 프로파일링 세션 중에 데이터 수집을 일시 중지하고 다시 시작할 수 있습니다.

 프로파일링 세션을 종료하려면 대상 애플리케이션을 닫고 프로파일러를 명시적으로 종료해야 합니다. 대부분의 경우 세션 종료 시 프로파일링 환경 변수를 지우는 것이 좋습니다.

## <a name="start-the-profiling-session"></a>프로파일링 세션 시작

#### <a name="to-start-profiling-by-using-the-instrumentation-method"></a>계측 방법을 사용하여 프로파일링을 시작하려면

1. 명령 프롬프트 창을 엽니다. 필요에 따라 PATH 환경 변수에 프로파일러 도구 디렉터리를 추가합니다. 경로는 설치 시 추가되지 않습니다.

2. **VSInstr** 도구를 사용하여 대상 애플리케이션의 계측된 버전을 생성합니다.

3. .NET Framework 프로파일링 환경 변수를 초기화합니다. 유형:

    **VSPerfClrEnv /traceon**

4. 프로파일러를 시작합니다. 유형:

    **VSPerfCmd /start:trace /output:** `OutputFile` [`Options`]

   - [/start](../profiling/start.md) **:trace** 옵션은 프로파일러를 초기화합니다.

   - **/start**에는 [/output](../profiling/output.md) **:** `OutputFile` 옵션이 필요합니다. `OutputFile`은 프로파일링 데이터(.vsp) 파일의 이름과 위치를 지정합니다.

     **/start:trace** 옵션과 다음 옵션 중 하나를 함께 사용할 수 있습니다.

   | 옵션 | 설명 |
   | - | - |
   | [/user](../profiling/user-vsperfcmd.md) **:** [`Domain` **\\** ]`UserName` | 프로파일링된 프로세스를 소유한 계정의 도메인 및 사용자 이름을 지정합니다. 이 옵션은 프로세스가 로그온한 사용자 이외의 사용자로 실행 중인 경우에만 필요합니다. Windows 작업 관리자의 **프로세스** 탭에 있는 **사용자 이름** 열에 프로세스 소유자가 나열됩니다. |
   | [/crosssession](../profiling/crosssession.md) | 프로세스 프로파일링 기능을 다른 세션에서 사용하도록 설정합니다. 이 옵션은 ASP.NET 애플리케이션이 다른 세션에서 실행 중인 경우 필요합니다. Windows 작업 관리자의 **프로세스** 탭에 있는 **세션 ID** 열에 세션 식별자가 나열됩니다. **/CS**를 **/crosssession**에 대한 약어로 지정할 수 있습니다. |
   | [/globaloff](../profiling/globalon-and-globaloff.md) | 데이터 수집을 일시 중지한 상태로 프로파일러를 시작합니다. [/globalon](../profiling/globalon-and-globaloff.md)을 사용하여 프로파일링을 다시 시작합니다. |
   | [/counter](../profiling/counter.md) **:** `Config` | `Config`에 지정된 프로세서 성능 카운터에서 정보를 수집합니다. 카운터 정보는 각 프로파일링 이벤트에서 수집되는 데이터에 추가됩니다. |
   | [/wincounter](../profiling/wincounter.md) **:** `WinCounterPath` | 프로파일링 중에 수집할 Windows 성능 카운터를 지정합니다. |
   | [/automark](../profiling/automark.md) **:** `Interval` | **/wincounter**와 함께 사용해야 합니다. Windows 성능 카운터 수집 이벤트 사이에 경과하는 시간(밀리초)을 지정합니다. 기본값은 500ms입니다. |
   | [/events](../profiling/events-vsperfcmd.md) **:** `Config` | 프로파일링 중에 수집할 ETW(Windows용 이벤트 추적) 이벤트를 지정합니다. ETW 이벤트는 별도의 파일(.*etl*)로 수집됩니다. |

5. 명령 프롬프트 창에서 대상 애플리케이션을 시작합니다.

## <a name="control-data-collection"></a>데이터 수집 제어
 대상 애플리케이션이 실행 중이면 *VSPerfCmd.exe* 옵션을 사용하여 프로파일러 데이터 파일에 대한 데이터 쓰기를 시작하고 중지하는 방식으로 데이터 수집을 제어할 수 있습니다. 데이터 수집을 제어하면 애플리케이션의 시작 또는 종료와 같이 프로그램 실행의 특정 부분에 대한 데이터를 수집할 수 있습니다.

#### <a name="to-start-and-stop-data-collection"></a>데이터 수집을 시작 및 중지하려면

- 다음 옵션 쌍을 사용하여 데이터 수집을 시작 및 중지합니다. 각 옵션을 개별 명령줄에서 지정합니다. 데이터 수집을 여러 번 켜고 끌 수 있습니다.

    |옵션|설명|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|모든 프로세스에 대한 데이터 수집을 시작( **/globalon**) 또는 중지( **/globaloff**)합니다.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|프로세스 ID(`PID`)로 지정된 프로세스에 대한 데이터 수집을 시작( **/processon**) 또는 중지( **/processoff**)합니다.|
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|스레드 ID(`TID`)로 지정된 스레드에 대한 데이터 수집을 시작( **/threadon**) 또는 중지( **/threadoff**)합니다.|

## <a name="end-the-profiling-session"></a>프로파일링 세션 종료
 프로파일링 세션을 종료하려면 계측된 구성 요소를 실행하는 애플리케이션을 닫습니다. 그런 다음 **VSPerfCmd** [/shutdown](../profiling/shutdown.md) 옵션을 호출하여 프로파일러를 끄고 프로파일링 데이터 파일을 닫습니다. **VSPerfClrEnv /off** 명령은 프로파일링 환경 변수를 지웁니다.

#### <a name="to-end-a-profiling-session"></a>프로파일링 세션을 종료하려면

1. 대상 애플리케이션을 닫습니다.

2. 프로파일러를 종료합니다. 유형:

     **VSPerfCmd /shutdown**

3. (선택 사항) 프로파일링 환경 변수를 지웁니다. 유형:

     **VSPerfClrEnv /off**

## <a name="see-also"></a>참고 항목
- [독립 실행형 애플리케이션 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [계측 방법 데이터 뷰](../profiling/instrumentation-method-data-views.md)