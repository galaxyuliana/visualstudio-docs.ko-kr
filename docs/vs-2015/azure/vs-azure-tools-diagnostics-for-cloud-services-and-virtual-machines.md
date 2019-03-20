---
title: Azure Cloud Services 및 virtual machines에 대 한 진단 설정 | Microsoft Docs
description: Azure 클라우드 서비스 및 Visual Studio에서 virtual machines (Vm) 디버깅에 대 한 진단을 설정 하는 방법에 알아봅니다.
author: mikejo5000
manager: douge
ms.assetid: e70cd7b4-6298-43aa-adea-6fd618414c26
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 06/28/2018
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 4448825c5d443887833a405aab14d2243a0e5216
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003073"
---
# <a name="set-up-diagnostics-for-azure-cloud-services-and-virtual-machines"></a>Azure Cloud Services 및 Virtual Machines에 대한 진단 설정
Azure 클라우드 서비스 또는 가상 머신 문제를 해결 해야 할 경우 Azure 진단을 보다 쉽게 설정 하 여 Visual Studio를 사용할 수 있습니다. 진단은 시스템 데이터와 로깅 데이터는 가상 머신과 클라우드 서비스를 실행 하는 가상 머신 인스턴스를 캡처합니다. 진단 데이터가 선택한 저장소 계정에 전송 됩니다. Azure에서 로깅 진단에 대 한 자세한 내용은 참조 [Azure App Service에서 웹 앱에 대 한 진단 로깅 설정](/azure/app-service/web-sites-enable-diagnostic-log)합니다.

이 문서에서는 보여드리겠습니다 설정 하 고 배포 전후에 Azure 진단을 설정 하려면 Visual Studio를 사용 하는 방법입니다. Azure virtual machines에서 진단을 설정 하는 방법, 수집할 진단 정보 유형을 선택 하는 방법 및 수집 된 정보를 확인 하는 방법에 알아봅니다.

Azure 진단을 설정 하려면 다음 옵션 중 하나를 사용할 수 있습니다.

* 진단 설정을 변경 합니다 **진단 구성** Visual Studio에서 대화 상자. 설정은은 diagnostics.wadcfgx (Azure SDK 2.4 및 이전 버전에서는 파일 이라고 diagnostics.wadcfg) 라는 파일에 저장 됩니다. 사용자 구성 파일을 직접 수정도 합니다. 파일을 수동으로 업데이트 하는 경우 구성 변경 내용이 적용 클라우드에 배포한 다음에 서비스를 Azure 또는 에뮬레이터에서 서비스를 실행 합니다.
* 클라우드 서비스 또는 실행 중인 가상 컴퓨터에 대 한 진단 설정을 변경 하려면 Visual Studio에서 클라우드 탐색기 또는 서버 탐색기를 사용 합니다.

## <a name="azure-sdk-26-diagnostics-changes"></a>Azure SDK 2.6 진단 변경
다음 변경 내용을 Azure SDK 2.6 및 Visual Studio에서 이상 프로젝트에 적용 됩니다.

* 로컬 에뮬레이터는 이제 진단을 지원합니다. 이 진단 데이터를 수집 하 고 개발 하 고 Visual Studio에서 테스트는 응용 프로그램에서 올바른 추적을 만들도록 확인 수를 의미 합니다. 연결 문자열 `UseDevelopmentStorage=true` Azure storage 에뮬레이터를 사용 하 여 Visual Studio에서 클라우드 서비스 프로젝트를 실행할 때는 진단 데이터 수집을 켭니다. 개발 저장소 저장소 계정에서 모든 진단 데이터 수집 됩니다.
* 진단 저장소 계정 연결 문자열을 `Microsoft.WindowsAzure.Plugins.Diagnostics.ConnectionString` 서비스 구성 (.cscfg) 파일에 저장 됩니다. Azure SDK 2.5에서는 진단 저장소 계정이 diagnostics.wadcfgx 파일에 지정 됩니다.

연결 문자열에서 몇 가지 주요 방식으로 Azure SDK 2.6 및 Azure SDK 2.4 및 나중에 하 버전에서 다르게 작동합니다.

* Azure SDK 2.4 및 이전 버전에서는 연결 문자열은 런타임으로 진단 플러그 인에 의해 진단 로그를 전송 하는 것에 대 한 저장소 계정 정보를 가져오려고 합니다.
* Azure SDK 2.6 이상 버전에서는 Visual Studio 진단 연결 문자열을 사용 하 여 게시 하는 동안 적절 한 저장소 계정 정보를 사용 하 여 Azure 진단 확장을 설정 합니다. 게시 하는 동안 Visual Studio를 사용 하는 다양 한 서비스 구성에 대 한 서로 다른 저장소 계정을 정의 하려면 연결 문자열을 사용할 수 있습니다. 그러나 Azure SDK 2.5 이후에 진단 플러그 인 사용할 수 없기 때문.cscfg 파일 자체만으로 진단 확장을 설정할 수 없습니다. Visual Studio 또는 PowerShell과 같은 도구를 사용 하 여 확장을 별도로 설정 해야 합니다.
* PowerShell을 사용 하 여 진단 확장을 설정 하는 프로세스를 간소화 하기 Visual Studio의 패키지 출력 한 각 역할에 대 한 진단 확장 공용 구성 XML을 포함 합니다. Visual Studio 진단 연결 문자열을 사용 하 여 공용 구성에서 저장소 계정 정보를 채웁니다. 공용 config 파일이 Extensions 폴더에 만들어집니다. 공용 config 파일이 명명 패턴 PaaSDiagnostics를 사용합니다. &lt;역할 이름\>합니다. PubConfig.xml 합니다. 모든 PowerShell 기반 배포가이 패턴을 사용 하 여 각 구성을 역할에 매핑할 수 있습니다.
* 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040) .cscfg 파일에서 연결 문자열을 사용 하 여 진단 데이터에 액세스 합니다. 데이터에 표시 되는 **모니터링** 탭 합니다. 연결 문자열은 포털에서 자세한 모니터링 데이터를 표시 하도록 서비스를 설정 해야 합니다.

## <a name="migrate-projects-to-azure-sdk-26-and-later"></a>Azure SDK 2.6 이상으로 프로젝트 마이그레이션
를 마이그레이션하는 경우 Azure SDK 2.6 이상으로 Azure SDK 2.5에서.wadcfgx 파일에 지정 된 진단 저장소 계정이 있으면 저장소 계정에는 해당 파일에 유지 됩니다. 다른 저장소 계정을 사용 하 여 서로 다른 저장소 구성에 대 한 유연성을 활용 하려면 수동으로 프로젝트에 연결 문자열을 추가 합니다. Azure SDK 2.4 또는 이전 버전에서 Azure SDK 2.6 프로젝트도 마이그레이션하는 경우 진단 연결 문자열이 유지 됩니다. 그러나 note는 Azure SDK 2.6을 이전 섹션에 설명 된 연결 문자열을 처리 하는 방식이 변경 합니다.

### <a name="how-visual-studio-determines-the-diagnostics-storage-account"></a>Visual Studio에서 진단 저장소 계정이 결정 하는 방법
* 진단 연결 문자열이.cscfg 파일에 지정 되어 게시할 때와 패키징 중 공용 구성 XML 파일을 생성 하는 경우 진단 확장을 설정 하려면 Visual Studio 사용 됩니다.
* 진단 연결 문자열이.cscfg 파일에 지정 하지 않으면, Visual Studio 사용 하도록 대체 진단 확장 공용 구성 XML을 생성 및 게시에 대 한 설정.wadcfgx 파일에 지정 된 저장소 계정 패키징 중 파일입니다.
* .Cscfg 파일에 진단 연결 문자열은.wadcfgx 파일의 저장소 계정 보다 우선합니다. 진단 연결 문자열이.cscfg 파일에 지정 된 Visual Studio 연결 문자열을 사용 하 여 하 고.wadcfgx의 저장소 계정은 무시 합니다.

### <a name="what-does-the-update-development-storage-connection-strings-check-box-do"></a>"개발 저장소 연결 문자열... 업데이트" 확인란의 기능은 무엇입니까?
합니다 **Microsoft Azure에 게시할 때 진단 및 캐싱을 위한 개발 저장소 연결 문자열을 Microsoft Azure 저장소 계정 자격 증명을 사용 하 여 업데이트** 확인란은 모든 개발 저장소를 업데이트 하는 편리한 방법 게시 하는 동안 지정 하는 Azure storage 계정을 사용 하 여 계정 연결 문자열입니다.

예를 들어이 확인란과 진단 연결 문자열을 선택 하면 지정 `UseDevelopmentStorage=true`프로젝트를 Azure에 게시할 때 Visual Studio에서 지정한 저장소 계정에 진단 연결 문자열을 자동으로 업데이트 게시 마법사입니다. 그러나 실제 저장소 계정을 진단 연결 문자열로 지정 된 경우 해당 계정이 대신 사용 됩니다.

## <a name="diagnostics-functionality-differences-in-azure-sdk-24-and-earlier-vs-azure-sdk-25-and-later"></a>Azure SDK 2.4 및 이전 vs 진단 기능 차이점입니다. Azure SDK 2.5 이상
프로젝트에서 Azure SDK 2.4 및 이전 Azure SDK 2.5 이상으로 업그레이드 하는 경우 염두에 다음 진단 기능 차이점:

* **구성 Api는 사용 되지 않습니다.** 합니다. 진단의 프로그래밍 방식 구성은 Azure SDK 2.4에서 사용할 수 있으며 이전에 있지만 Azure SDK 2.5에서 이상 사용 되지 않습니다. 에 진단 구성이 현재 정의 된 경우 코드에서 진단을 위해 마이그레이션된 프로젝트에서 처음부터 계속 작업 하려면 이러한 설정을 다시 구성 해야 합니다. Azure SDK 2.4 용 진단 구성 파일은 diagnostics.wadcfg입니다. Azure SDK 2.5 이상용 진단 구성 파일은 diagnostics.wadcfg입니다.
* **클라우드 서비스 응용 프로그램에 대 한 진단은 역할 수준 에서만 구성할 수 있습니다**합니다. Azure SDK 2.5 이상 버전에서는 클라우드 서비스 응용 프로그램에 대 한 진단 인스턴스 수준에서 설정할 수 없습니다.
* **앱을 배포할 때마다 진단 구성이 업데이트 됨**합니다. Visual Studio 서버 탐색기에서 진단 구성을 변경한 후 앱을 다시 배포 하는 경우 패리티 문제가 발생할 수 있습니다.
* **코드에서가 아닌 진단 구성 파일에 크래시 덤프가 구성 된 Azure SDK 2.5 이상에서는**합니다. 크래시 덤프 코드에 구성 된 경우 구성 파일에 코드에서 구성을 수동으로 전송 해야 있습니다. Azure SDK 2.6으로 마이그레이션하는 동안 크래시 덤프가 전송 되지 않습니다.

## <a name="turn-on-diagnostics-in-cloud-service-projects-before-you-deploy-them"></a>배포 하기 전에 클라우드 서비스 프로젝트에서 진단 켜기
Visual Studio에서 배포 하기 전에 에뮬레이터에서 서비스를 실행할 때 Azure에서 실행 되는 역할에 대 한 진단 데이터를 수집할 수 있습니다. 모든 Visual Studio에서 진단 설정 변경 내용은 diagnostics.wadcfgx 구성 파일에 저장 됩니다. 이러한 설정은 클라우드 서비스를 배포할 때 진단 데이터가 저장 되는 저장소 계정을 지정 합니다.

[!INCLUDE [cloud-services-wad-warning](./includes/cloud-services-wad-warning.md)]

### <a name="to-turn-on-diagnostics-in-visual-studio-before-deployment"></a>배포 하기 전에 Visual Studio에서 진단을 켜려면

1. 역할에 대 한 바로 가기 메뉴에서 선택 **속성**합니다. 역할의 **속성** 대화 상자를 선택 합니다 **구성** 탭 합니다.
2. 에 **진단** 섹션에서 확인 합니다 **진단을 사용 하도록 설정** 확인란을 선택 합니다.
   
    ![진단 사용 옵션 액세스](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796660.png)
3. 진단 데이터에 대 한 저장소 계정을 지정 하려면 줄임표 (...) 단추를 선택 합니다.
   
    ![사용할 저장소 계정을 지정 합니다.](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796661.png)
4. 에 **저장소 연결 문자열 만들기** 대화 상자에서 Azure storage 에뮬레이터, Azure 구독을 사용 하 여 연결 하려면 아니면 수동으로 자격 증명을 입력할지 여부를 지정 합니다.
   
    ![저장소 계정 대화 상자](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796662.png)
   
   * 선택 하는 경우 **Microsoft Azure storage 에뮬레이터**, 연결 문자열 설정은 `UseDevelopmentStorage=true`합니다.
   * 선택 하는 경우 **구독의**를 사용 하려는 Azure 구독을 선택 하는 계정 이름을 입력 합니다. Azure 구독을 관리 하려면 선택 **계정 관리**합니다.
   * 선택 하는 경우 **수동으로 입력 한 자격 증명**, 이름 및 사용 하려는 Azure 계정의 키를 입력 합니다.
5. 보려는 합니다 **진단 구성을** 대화 상자에서 **구성**합니다. 제외 하 고 **일반적인** 하 고 **로그 디렉터리**, 각 탭에는 수집할 수 있는 진단 데이터 원본을 나타냅니다. 기본값 **일반** 탭 다음 진단 데이터 컬렉션 옵션을 제공 합니다. **오류만**, **모든 정보**, 및 **사용자 지정 계획**. 기본값 **오류만** 옵션은 경고 또는 추적 메시지를 전송 하지 않으므로 최소한의 저장소를 사용 합니다. 합니다 **정보를 모두** 옵션은 대부분의 정보를 전송, 대부분의 저장소를 사용 하 여 이며 따라서 가장 비용이 많이 드는 옵션입니다.

   > [!NOTE]
   > "디스크 할당량의 MB"에 대 한 최소 지원 되는 크기는 4GB입니다. 그러나 메모리 덤프를 수집 하는 경우까지 늘릴 10GB와 같은 더 높은 값입니다.
   >
  
    ![Azure Diagnostics 및 구성 사용](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758144.png)
6. 예를 들어 다음을 선택 합니다 **사용자 지정 계획** 옵션, 수집 된 데이터를 사용자 지정할 수 있습니다.
7. 에 **디스크 할당량 (mb)** 상자에서는 진단 데이터에 대 한 저장소 계정에 할당할 공간을 설정할 수 있습니다. 변경 하거나 기본값을 그대로 적용 수 있습니다.
8. 수집 하려는 진단 데이터의 각 탭을 선택 합니다 **전송 사용 \<로그 유형\>**  확인란 합니다. 예를 들어, 응용 프로그램 로그에서 수집 하려는 경우는 **응용 프로그램 로그** 탭을 선택 합니다 **응용 프로그램 로그 전송 사용** 확인란 합니다. 또한 각 진단 데이터 형식에 필요한 기타 정보를 지정 합니다. 각 탭에 대 한 구성 정보를 보려면 **진단 데이터 원본 설정** 이 문서의 뒷부분에 나오는. 
9. 원하는 모든 진단 데이터의 컬렉션을 설정한 후 선택할 **확인**합니다.
10. 일반적으로 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 실행 합니다. 응용 프로그램을 사용 하도록 설정한 로그 정보가 지정한 Azure storage 계정에 저장 됩니다.

## <a name="turn-on-diagnostics-on-azure-virtual-machines"></a>Azure virtual machines에서 진단 켜기
Visual Studio에서 Azure virtual machines에 대 한 진단 데이터를 수집할 수 있습니다.

### <a name="to-turn-on-diagnostics-on-azure-virtual-machines"></a>Azure virtual machines에서 진단을 켜려면

1. 서버 탐색기에서 Azure 노드를 선택한 다음 연결 되어 있지 않은 경우 Azure 구독에 연결 합니다.
2. 확장 된 **가상 머신** 노드. 새 가상 머신을 만들거나 기존 노드를 선택할 수 있습니다.
3. 가상 컴퓨터에 대 한 바로 가기 메뉴에서 선택 **구성**합니다. 가상 머신 구성 대화 상자가 나타납니다.
   
    ![Azure 가상 머신 구성](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796663.png)
4. 설치 되어 있지 않은 경우 Microsoft Monitoring Agent 진단 확장을 추가 합니다. 이 확장을 통해 Azure 가상 머신에 대 한 진단 데이터를 수집할 수 있습니다. 아래 **설치 된 확장**를 **사용 가능한 확장 선택** 드롭다운 목록 상자에서 **Microsoft Monitoring Agent 진단**합니다.
   
    ![Azure 가상 머신 확장 설치](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766024.png)
   
    > [!NOTE]
   > 다른 진단 확장은 가상 머신에 대해 사용할 수 있습니다. 자세한 내용은 [Windows 용 가상 머신 확장 및 기능](https://docs.microsoft.com/azure/virtual-machines/windows/extensions-features)합니다.
   > 
   > 
5. 확장 및 보기를 추가 하려면 해당 **진단 구성을** 대화 상자에서 **추가**합니다.
6. 저장소 계정을 지정 하려면 **구성**를 선택한 후 **확인**합니다.
   
    각 탭 (제외한 **일반적인** 하 고 **로그 디렉터리**) 수집할 수 있는 진단 데이터 원본을 나타냅니다.
   
    ![Azure Diagnostics 및 구성 사용](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758144.png)
   
    기본 탭 인 **일반**, 다음과 같은 진단 데이터 컬렉션 옵션 제공: **오류만**를 **모든 정보**, 및 **사용자지정계획**. 기본 옵션인 **오류만**, 경고 또는 추적 메시지를 전송 하지 않으므로 최소한의 저장소를 사용 합니다. 합니다 **정보를 모두** 옵션은 대부분의 정보를 전송 되며, 따라서 저장소를 기준으로 가장 비용이 많이 드는 옵션입니다.
7. 예를 들어 다음을 선택 합니다 **사용자 지정 계획** 수집 옵션 데이터를 사용자 지정할 수 있습니다.
8. 합니다 **디스크 할당량 (mb)** 상자 할당 하려는 저장소 계정에 진단 데이터에 대 한 공간을 지정 합니다. 원하는 경우 기본값을 변경할 수 있습니다.
9. 수집 하려는 진단 데이터의 각 탭에서 해당 **전송 사용 \<로그 유형\>**  확인란 합니다.
   
    응용 프로그램 로그를 수집 하려는 경우 선택 하는 예를 들어 합니다 **응용 프로그램 로그 전송 사용** 확인란 합니다 **응용 프로그램 로그** 탭 합니다. 또한 각 진단 데이터 형식에 필요한 기타 정보를 지정 합니다. 각 탭에 대 한 구성 정보를 보려면 **진단 데이터 원본 설정** 이 문서의 뒷부분에 나오는.
10. 원하는 모든 진단 데이터 수집을 활성화 한 후 선택 **확인**합니다.
11. 업데이트 된 프로젝트를 저장 합니다.
    
    메시지를 **Microsoft Azure 활동 로그** 창 가상 컴퓨터에 업데이트 되었음을 나타냅니다.

## <a name="set-up-diagnostics-data-sources"></a>진단 데이터 원본 설정
진단 데이터 수집을 활성화 한 후에 어떤 데이터 원본이 정확 하 게 하려면를 수집 하 고 수집 되는 정보를 선택할 수 있습니다. 다음 섹션은 탭을 설명 합니다 **진단 구성** 대화 상자와 각 구성 옵션을 의미 합니다.

### <a name="application-logs"></a>응용 프로그램 로그
응용 프로그램 로그는 웹 응용 프로그램에서 생성 되는 진단 정보를 포함 합니다. 응용 프로그램 로그를 수집 하려는 경우 선택 합니다 **응용 프로그램 로그 전송 사용** 확인란 합니다. 저장소 계정에 응용 프로그램 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다. 설정 하 여 로그에 캡처되는 정보의 양을 변경할 수도 있습니다는 **로그 수준** 값입니다. 예를 들어, 선택 **Verbose** 선택 하거나 자세한 내용을 보려면 **위험** 중요 한 오류만 캡처해야 합니다. 응용 프로그램 로그를 내보내는 특정 진단 공급자가 있으면 공급자의 GUID를 추가 하 여 로그를 캡처할 수 있습니다 합니다 **공급자 GUID** 상자입니다.

  ![응용 프로그램 로그](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758145.png)

응용 프로그램 로그에 대 한 자세한 내용은 참조 하세요. [Azure App Service에서 웹 앱에 대 한 진단 로깅 설정](/azure/app-service/web-sites-enable-diagnostic-log)합니다.

### <a name="windows-event-logs"></a>Windows 이벤트 로그
Windows 이벤트 로그를 캡처하려면 다음을 선택 합니다 **Windows 이벤트 로그 전송 사용** 확인란 합니다. 저장소 계정으로의 이벤트 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다. 추적 하려는 이벤트 유형에 대 한 확인란을 선택 합니다.

![이벤트 로그](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796664.png)

Azure SDK 2.6 이상을 사용 하는 사용자 지정 데이터 원본을 지정 하려는 경우에 입력 합니다 **\<데이터 원본 이름\>** 텍스트 상자를 선택한 후 **추가**합니다. 데이터 원본 diagnostics.cfcfg 파일에 추가 됩니다.

Azure SDK 2.5를 사용 하는 사용자 지정 데이터 원본을 지정 하고자 하는 경우 추가할 수 있습니다 하는 `WindowsEventLog` 부분 diagnostics.wadcfgx 파일을 같은 다음 예제에서:

```
<WindowsEventLog scheduledTransferPeriod="PT1M">
   <DataSource name="Application!*" />
   <DataSource name="CustomDataSource!*" />
</WindowsEventLog>
```
### <a name="performance-counters"></a>성능 카운터
성능 카운터 정보를 사용 하 여 시스템 병목 지점을 찾고 시스템 및 응용 프로그램 성능을 미세 조정할 수 있습니다. 자세한 내용은 [Azure 응용 프로그램에서 성능 카운터 만들기 및 사용 하 여](https://msdn.microsoft.com/library/azure/hh411542.aspx)입니다. 성능 카운터를 캡처하려면 다음을 선택 합니다 **성능 카운터 전송 사용** 확인란 합니다. 저장소 계정으로의 이벤트 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다. 추적 하려는 성능 카운터에 대 한 확인란을 선택 합니다.

![성능 카운터](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758147.png)

나열 되지 않은 성능 카운터를 추적 하려면 제안 된 구문을 사용 하 여 성능 카운터를 입력 합니다. 선택한 후 **추가**합니다. 가상 머신에서 운영 체제를 추적할 수 있습니다 하는 성능 카운터를 확인 합니다. 구문에 대 한 자세한 내용은 참조 하십시오 [카운터 경로 지정](https://msdn.microsoft.com/library/windows/desktop/aa373193.aspx)합니다.

### <a name="infrastructure-logs"></a>인프라 로그
인프라 로그는 Azure 진단 인프라, RemoteAccess 모듈 및 RemoteForwarder 모듈에 대 한 정보를 포함합니다. 인프라 로그에 대 한 정보를 수집 하려면 선택 합니다 **인프라 로그 전송 사용** 확인란 합니다. 저장소 계정으로의 인프라 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다.

![진단 인프라 로그](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758148.png)

자세한 내용은 [Azure 진단을 사용 하 여 로깅 데이터 수집](https://msdn.microsoft.com/library/azure/gg433048.aspx)합니다.

### <a name="log-directories"></a>로그 디렉터리
로그 디렉터리에 인터넷 정보 서비스 (IIS) 요청, 실패 한 요청 또는 선택한 폴더에 대 한 로그 디렉터리에서 수집 된 데이터가 있습니다. 로그 디렉터리를 캡처하려면 다음을 선택 합니다 **로그 디렉터리 전송 사용** 확인란 합니다. 저장소 계정으로의 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다.

와 같은 수집 하려는 로그의 확인란을 선택 **IIS 로그** 하 고 **실패 한 요청** 로그 합니다. 기본 저장소 컨테이너 이름이 제공 되지만 이름을 변경할 수 있습니다.

모든 폴더에서 로그를 캡처할 수 있습니다. 에 포함 된 경로 지정 합니다 **절대 디렉터리에서 로그** 섹션을 선택한 후 **디렉터리 추가**합니다. 로그는 지정된 된 컨테이너에 캡처됩니다.

![로그 디렉터리](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796665.png)

### <a name="etw-logs"></a>ETW 로그
사용 하는 경우 [Windows 이벤트 추적에 대 한](https://msdn.microsoft.com/library/windows/desktop/bb968803\(v=vs.85\).aspx) (ETW) 및 ETW 로그를 수집 하려면 선택 합니다 **ETW 로그 전송 사용** 확인란 합니다. 저장소 계정으로의 로그 전송 간격을 늘리거나 변경 합니다 **전송 기간 (분)** 값입니다.

이벤트는 이벤트 원본과 이벤트 매니페스트에서 지정한에서 캡처됩니다. 이벤트 소스를 지정 하는 **이벤트 원본** 섹션 이름을 입력 하 고 선택한 **이벤트 원본 추가**합니다. 마찬가지로,에서 이벤트 매니페스트를 지정할 수 있습니다 합니다 **이벤트 매니페스트** 섹션을 선택한 후 **이벤트 매니페스트 추가**합니다.

![ETW 로그](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766025.png)

ETW 프레임 워크의 클래스를 통해 ASP.NET에서 지원 되는 [System.Diagnostics.aspx](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110)) 네임 스페이스입니다. Microsoft.WindowsAzure.Diagnostics 네임 스페이스에서 상속 하며 표준 확장 [System.Diagnostics.aspx](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110)) 클래스를 사용할 수 있도록 [System.Diagnostics.aspx](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110)) 로 로깅 Azure 환경에서 프레임 워크입니다. 자세한 내용은 [Microsoft Azure에서 로깅 및 추적을 제어할](https://msdn.microsoft.com/magazine/ff714589.aspx) 하 고 [Azure Cloud Services 및 virtual machines에서 진단을 사용 하도록 설정](/azure/cloud-services/cloud-services-dotnet-diagnostics)합니다.

### <a name="crash-dumps"></a>크래시 덤프
역할 인스턴스가 충돌 하는 경우에 대 한 정보를 캡처하려면 다음을 선택 합니다 **크래시 덤프 전송 사용** 확인란 합니다. (대부분의 예외를 처리 하는 ASP.NET, 때문에 이것이 일반적으로 작업자 역할에만 유용 합니다.) 크래시 덤프에 사용 된 저장소 공간의 비율을 늘리거나 변경 합니다 **디렉터리 할당량 (%)** 값입니다. 크래시 덤프가 저장 됩니다 및 캡처를 검색할지를 선택 합니다. 여기서 저장소 컨테이너를 변경할 수는 **전체** 하거나 **미니** 덤프 합니다.

현재 추적 중인 프로세스가 다음 스크린샷에 나열 됩니다. 캡처하려는 프로세스에 대 한 확인란을 선택 합니다. 다른 프로세스를 목록에 추가 하려면 프로세스 이름을 입력 하 고 선택한 **프로세스 추가**합니다.

![크래시 덤프](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766026.png)

자세한 내용은 [Microsoft Azure에서 로깅 및 추적을 제어할](https://msdn.microsoft.com/magazine/ff714589.aspx) 하 고 [Microsoft Azure 진단 4 부: 사용자 지정 로깅 구성 요소 및 Azure 진단 1.3 변경 내용](http://justazure.com/microsoft-azure-diagnostics-part-4-custom-logging-components-azure-diagnostics-1-3-changes/)합니다.

## <a name="view-the-diagnostics-data"></a>진단 데이터 보기
클라우드 서비스 또는 가상 컴퓨터에 대 한 진단 데이터를 수집한 후에이 볼 수 있습니다.

### <a name="to-view-cloud-service-diagnostics-data"></a>클라우드 서비스 진단 데이터를 보려면
1. 를 일반적인 방법으로 클라우드 서비스를 배포 하 고 실행 합니다.
2. 저장소 계정에 Visual Studio에서 생성 하는 보고서 또는 테이블에서 진단 데이터를 볼 수 있습니다. 클라우드 탐색기 또는 서버 탐색기는 보고서의 데이터에는 선택한 역할에 대 한 노드의 바로 가기 메뉴를 열고 보기로 **진단 데이터 보기**합니다.
   
    ![진단 데이터 보기](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC748912.png)
   
    사용 가능한 데이터를 표시 하는 보고서에는 다음이 표시 됩니다.
   
    ![Visual Studio에서 Microsoft Azure 진단 보고서](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796666.png)
   
    최신 데이터가 표시 되지 않을 경우 전송 기간이 경과할 때까지 대기 해야 합니다.
   
    데이터를 즉시 업데이트 하려면 선택 합니다 **새로 고침** 링크 합니다. 데이터를 자동으로 업데이트 하도록에서 간격을 선택 합니다 **자동 새로 고침** 드롭다운 목록 상자입니다. 오류 데이터를 내보내려면 선택 합니다 **CSV로 내보내기** 단추를 Excel 워크시트의 열 수 있는 쉼표로 구분 된 값 파일을 만듭니다.
   
    클라우드 탐색기 또는 서버 탐색기에서 배포와 연결 된 저장소 계정을 엽니다.
3. 테이블 뷰어에서 진단 테이블을 열 및 수집한 데이터 검토 합니다. 사용자 지정 로그와 IIS 로그에 대 한 blob 컨테이너를 열 수 있습니다. 다음 표에서 테이블 또는 다른 로그 파일에 대 한 데이터가 포함 된 blob 컨테이너를 나열 합니다. 로그 파일에 대 한 데이터 외에도 테이블 항목을 포함 **EventTickCount**, **DeploymentId**하십시오 **역할**, 및 **RoleInstance** 에 가상 머신과 역할 생성 데이터를 식별할 수 있도록 및 시기입니다. 
   
   | 진단 데이터 | 설명 | 위치 |
   | --- | --- | --- |
   | 응용 프로그램 로그 |코드의 메서드를 호출 하 여 생성 된 로그는 **System.Diagnostics.Trace** 클래스입니다. |WADLogsTable |
   | 이벤트 로그 |가상 머신에서 Windows 이벤트 로그에서 데이터를 제공 합니다. 이러한 로그에 정보를 저장 하는 Windows 하지만 응용 프로그램 및 서비스에서는 로그 오류 보고를 사용 하 여 또는 로그 정보입니다. |WADWindowsEventLogsTable |
   | 성능 카운터 |가상 머신에서 사용할 수 있는 성능 카운터에서 데이터를 수집할 수 있습니다. 운영 체제에서 메모리 사용량 및 프로세서 시간 등의 여러 통계를 포함 하는 성능 카운터를 제공 합니다. |WADPerformanceCountersTable |
   | 인프라 로그 |진단 인프라 자체에서 생성 된 로그입니다. |WADDiagnosticInfrastructureLogsTable |
   | IIS 로그 |웹 요청을 기록 하는 로그입니다. 클라우드 서비스에는 상당한 양의 트래픽 가져옵니다, 이러한 로그 시간이 오래 걸릴 수 있습니다. 수집 하 고 필요한 경우에이 데이터를 저장 하는 것이 좋습니다. |Wad-iis-failedreqlogs, 배포, 역할 및 인스턴스에 대 한 경로 아래의 blob 컨테이너에서 실패 한 요청 로그를 확인할 수 있습니다. Wad-iis-로그 파일에서 전체 로그를 찾을 수 있습니다. 각 파일에 대 한 항목은 WADDirectories 테이블에서 수행 됩니다. |
   | 크래시 덤프 |클라우드 서비스의 프로세스 (일반적으로 작업자 역할)의 이진 이미지를 제공합니다. |wad 충돌 덤프 blob 컨테이너 |
   | 사용자 지정 로그 파일 |미리 정의 된 데이터의 로그입니다. |지정할 수 있습니다 코드에서 사용자 지정 로그 파일의 위치에서 저장소 계정. 예를 들어, 사용자 지정 blob 컨테이너를 지정할 수 있습니다. |
4. 임의 형식의 데이터가 잘린 경우 해당 데이터에 대 한 버퍼를 늘리거나 시도할 수 있습니다 형식 또는 저장소 계정에 가상 컴퓨터에서 데이터 전송 사이의 간격을 단축 합니다.
5. (선택 사항) 전체 저장소 비용을 절감 하는 경우도 저장소 계정에서 데이터를 제거 합니다.
6. 전체 배포를 수행 하는 경우에 Azure에서 diagnostics.cscfg 파일 (.wadcfgx Azure SDK 2.5 용) 업데이트 되 고 클라우드 서비스 진단 구성에 모든 변경 내용이 적용. 대신에 기존 배포를 업데이트 하는 경우 Azure에서.cscfg 파일 업데이트 되지 않습니다. 여전히 진단 설정을 다음 단원의 단계를 수행 하지만 변경할 수 있습니다. 전체 배포 및 기존 배포를 업데이트 하는 방법에 대 한 자세한 내용은 참조 하세요. [Azure 응용 프로그램 게시 마법사](vs-azure-tools-publish-azure-application-wizard.md)합니다.

### <a name="to-view-virtual-machine-diagnostics-data"></a>가상 머신 진단 데이터를 보려면
1. 가상 컴퓨터에 대 한 바로 가기 메뉴에서 선택 **진단 데이터 보기**합니다.
   
    ![Azure virtual machine에서 진단 데이터 보기](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766027.png)
   
    합니다 **진단 요약** 대화 상자가 나타납니다.
   
    ![Azure 가상 머신 진단 요약](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796667.png)  
   
    최신 데이터가 표시 되지 않을 경우 전송 기간이 경과할 때까지 대기 해야 합니다.
   
    데이터를 즉시 업데이트 하려면 선택 합니다 **새로 고침** 링크 합니다. 데이터를 자동으로 업데이트 하도록에서 간격을 선택 합니다 **자동 새로 고침** 드롭다운 목록 상자입니다. 오류 데이터를 내보내려면 선택 합니다 **CSV로 내보내기** 단추를 Excel 워크시트의 열 수 있는 쉼표로 구분 된 값 파일을 만듭니다.

## <a name="set-up-cloud-service-diagnostics-after-deployment"></a>배포 후 클라우드 서비스 진단 설정
지정 하지 않은 데이터를 수집 하려는 경우 이미 실행 중인 클라우드 서비스를 사용 하 여 문제를 조사 하는 역할을 처음 배포 하기 전에 합니다. 이 경우 서버 탐색기에서 설정을 변경 하 여 해당 데이터의 수집을 시작할 수 있습니다. 단일 인스턴스 또는 열었는지에 따라 역할의 모든 인스턴스에 대 한 진단을 설정할 수 있습니다 합니다 **진단 구성** 또는 역할 인스턴스에 대 한 바로 가기 메뉴에서 대화 상자. 역할 노드를 구성 하는 경우 모든 변경 내용이 모든 인스턴스에 적용 됩니다. 인스턴스 노드를 구성 하는 경우 변경한 내용이 해당 인스턴스에만 적용 됩니다.

### <a name="to-set-up-diagnostics-for-a-running-cloud-service"></a>실행 중인 클라우드 서비스에 대 한 진단을 설정 하려면
1. 서버 탐색기에서 확장을 **Cloud Services** 노드를 펼친 다음 역할 인스턴스 (또는 둘 다)을 찾으려고 노드 목록을 조사 하려는.
   
    ![진단 구성](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC748913.png)
2. 인스턴스 노드나 역할 노드에 대 한 바로 가기 메뉴에서 선택 **진단 설정 업데이트**을 수집 하려는 진단 설정을 선택 합니다.
   
    구성 설정에 대 한 자세한 내용은 섹션을 참조 하세요 **진단 데이터 원본 설정** 이 문서의. 진단 데이터를 보는 방법에 대 한 자세한 내용은 섹션을 참조 하세요 **진단 데이터 보기** 이 문서의.
   
    서버 탐색기에서 데이터 수집을 변경한 경우 클라우드 서비스를 완전히 다시 배포할 때까지 변경 내용을 적용 유지. 기본값을 사용 하는 경우 게시 설정, 변경 내용을 덮어쓰지 않습니다. 기본 게시 설정이 전체 재배포를 수행 하기 보다는 기존 배포를 업데이트 하는 합니다. 설정을 배포 시의 선택을 취소 되도록로 이동 합니다 **고급 설정** 게시 마법사에서 탭 한 다음 선택을 취소를 **배포 업데이트** 확인란 합니다. 통해 집합으로 설정이 되돌립니다.wadcfgx (또는.wadcfg) 파일의 해당 확인란을 선택 취소, 다시 배포 하면 합니다 **속성** 역할에 대 한 편집기입니다. 배포를 업데이트 하는 경우 Azure는 이전 설정을 유지 합니다.

## <a name="troubleshoot-azure-cloud-service-issues"></a>Azure 클라우드 서비스 문제 해결
"사용 중" 상태에 고착 된 역할, 반복적인 재활용 또는 내부 서버 오류 throw와 같은 클라우드 서비스 프로젝트에서 문제가 발생 하면 도구와 진단 및 문제를 해결 하는 데 사용할 수 있는 기술이 있습니다. 일반적인 문제 및 솔루션의 특정 예제 및 개념 및 진단 하 고 이러한 오류를 해결 하는 데 사용할 수 있는 도구에 대 한 개요를 참조 하세요 [Azure PaaS compute 진단 데이터](http://blogs.msdn.com/b/kwill/archive/2013/08/09/windows-azure-paas-compute-diagnostics-data.aspx)입니다.

## <a name="q--a"></a>Q&A
**버퍼 크기를 무엇이 고 얼마나 큰 깁 니 까?**

각 가상 컴퓨터 인스턴스에 대 한 할당량 제한 로컬 파일 시스템에 얼마나 많은 진단 데이터를 저장할 수 있습니다. 또한 사용할 수 있는 진단 데이터의 각 형식에 대 한 버퍼 크기를 지정할 수 있습니다. 이 버퍼 크기는 해당 형식의 데이터에 대 한 개별 할당량을 처럼 작동합니다. 전체 할당량과 남은 메모리의 크기를 확인 하려면 진단 데이터 형식에 대 한 대화 상자의 맨 아래를 참조 하세요. 더 큰 버퍼 또는 더 다양 한 유형의 데이터를 지정 하는 경우에 전체 할당량을 근접 하 게 됩니다. Diagnostics.wadcfg 또는.wadcfgx 구성 파일을 수정 하 여 전체 할당량을 변경할 수 있습니다. 진단 데이터는 응용 프로그램의 데이터와 같은 파일 시스템에 저장 됩니다. 많은 양의 디스크 공간을 사용 하 여 응용 프로그램에는 전체 진단 할당량을 늘리지 말아야 합니다.

**전송 기간 이란 무엇 이며 어떻게 기간이 깁 니 까?**

전송 기간은 데이터 간에 경과 되 캡처하는 시간의 양입니다. 각 전송 기간 후 데이터는 로컬 파일 시스템에서 가상 컴퓨터에서 테이블로 이동 저장소 계정에 있습니다. 수집 되는 데이터 양을 전송 기간이 끝나기 전에 할당량을 초과 하는 경우 이전 데이터 삭제 됩니다. 데이터 버퍼 크기 또는 전체 할당량을 초과 하기 때문에 데이터를 손실 되는, 하는 경우 전송 기간을 줄일 것이 좋습니다.

**타임 스탬프에는 어떤 시간대가?**

타임 스탬프는 클라우드 서비스를 호스팅하는 데이터 센터의 현지 표준 시간대입니다. 로그 테이블에 다음 세 타임 스탬프 열이 사용 됩니다.

* **PreciseTimeStamp**: 이벤트의 ETW 타임 스탬프입니다. 즉, 클라이언트에서 이벤트는 로그에 있습니다.
* **타임 스탬프**: 값 **PreciseTimeStamp** 업로드 빈도 경계로 내림 합니다. 예를 들어 업로드 빈도가 5 분이 고 이벤트 시간이 00시 17분: 12 인 경우 타임 스탬프는 00시 15분: 00입니다.
* **타임 스탬프**: Azure 테이블에서 엔터티를 만든 타임 스탬프입니다.

**진단 정보를 수집 하는 경우 비용을 관리 하는 방법**

기본 설정 (**로그 수준** 로 설정 **오류**, 및 **전송 기간** 로 **1 분**) 비용을 최소화 하기 위한 것입니다. 계산 비용이 더 많은 진단 데이터를 수집 하거나 전송 기간을 줄이는 경우 늘어납니다. 필요한을 더 이상 필요할 때 데이터 수집을 사용 하지 않도록 설정 해야 하는 보다 더 많은 데이터를 수집 하지 마십시오. 하면 항상 사용 하도록 설정할 수 다시 실행된 시간에도이 문서의 앞부분에 설명 된 대로 합니다.

**IIS에서 실패 한 요청 로그를 수집 어떻게**

기본적으로 IIS는 실패 한 요청 로그를 수집 하지 않습니다. 웹 역할에 대 한 web.config 파일을 편집 하 여 실패 한 요청 로그를 수집 하도록 IIS를 설정할 수 있습니다.

**OnStart 같은 RoleEntryPoint 메서드에서 추적 정보를 받을 수 없는 합니다. 무엇이 문제입니까?**

메서드 **RoleEntryPoint** IIS에 없는 WAIISHost.exe 컨텍스트에서 호출 됩니다. 추적을 사용이 적용 되지 않습니다는 일반적으로 web.config에 구성 정보입니다. 이 문제를 해결 하려면 웹 역할 프로젝트에.config 파일을 추가 하 고 포함 된 출력 어셈블리와 일치 하는 파일 이름을 합니다 **RoleEntryPoint** 코드입니다. 기본 웹 역할 프로젝트에서.config 파일의 이름은 waiishost.exe.config가 됩니다 이어야 합니다. 이 파일에 다음 줄을 추가 합니다.

```
<system.diagnostics>
  <trace>
      <listeners>
          <add name “AzureDiagnostics” type=”Microsoft.WindowsAzure.Diagnostics.DiagnosticMonitorTraceListener”>
              <filter type=”” />
          </add>
      </listeners>
  </trace>
</system.diagnostics>
```

에 **속성** 창에서 설정 합니다 **출력 디렉터리로 복사** 속성을 **항상 복사**.

## <a name="next-steps"></a>다음 단계
Azure에서 로깅 진단에 대 한 자세한 내용은 참조 하세요 [Azure Cloud Services 및 virtual machines에서 진단을 사용 하도록 설정](/azure/cloud-services/cloud-services-dotnet-diagnostics.md) 하 고 [Azure App Service에서 웹 앱에 대 한 진단 로깅 설정](/azure/app-service/web-sites-enable-diagnostic-log)합니다.

