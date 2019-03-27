---
title: Visual Studio에서 Azure 클라우드 서비스에 대 한 역할 구성 | Microsoft Docs
description: 설정 및 Visual Studio를 사용 하 여 Azure 클라우드 서비스에 대 한 역할을 구성 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: d397ef87-64e5-401a-aad5-7f83f1022e16
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: ce2259debb55c4792c2998f0e67df69dbc8cb7f9
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003078"
---
# <a name="configure-azure-cloud-service-roles-with-visual-studio"></a>Visual Studio를 사용하여 Azure 클라우드 서비스 역할 구성
Azure 클라우드 서비스 작업자 또는 웹 역할을 하나 이상 있을 수 있습니다. 각 역할에 대해 해당 역할 설정 하는 방법을 정의 하 고 해당 역할을 실행 하는 방법을 구성 해야 합니다. Cloud services의 역할에 대 한 자세한 내용은 비디오 참조 [Azure Cloud Services 소개](https://channel9.msdn.com/Series/Windows-Azure-Cloud-Services-Tutorials/Introduction-to-Windows-Azure-Cloud-Services)합니다. 

클라우드 서비스에 대 한 정보는 다음 파일에 저장 됩니다.

- **ServiceDefinition.csdef** -서비스 정의 파일에는 프로그램은 필요한 역할을 포함 하 여 클라우드 서비스, 끝점 및 가상 머신 크기에 대 한 런타임 설정을 정의 합니다. 에 저장 된 데이터가 없는 `ServiceDefinition.csdef` 역할이 실행 중인 경우에 변경할 수 있습니다.
- **ServiceConfiguration.cscfg** -얼마나 많은 역할의 인스턴스가 실행 되는 서비스 구성 파일을 구성 하 고 역할에 대해 정의 된 설정의 값입니다. 저장 된 데이터 `ServiceConfiguration.cscfg` 역할이 실행 중인 동안 변경할 수 있습니다.

역할을 실행 하는 방법을 제어 하는 설정에 대해 다른 값을 저장 하려면 여러 서비스 구성을 정의할 수 있습니다. 각 배포 환경에 대 한 다른 서비스 구성을 사용할 수 있습니다. 예를 들어, 로컬 서비스 구성에서 로컬 Azure 저장소 에뮬레이터를 사용 하 고 클라우드에서 Azure storage를 사용 하도록 다른 서비스 구성을 만들 저장소 계정 연결 문자열을 설정할 수 있습니다.

Visual Studio에서 Azure 클라우드 서비스를 만들 때 두 개의 서비스 구성이 자동으로 생성 되어 Azure 프로젝트에 추가 합니다.

- `ServiceConfiguration.Cloud.cscfg`
- `ServiceConfiguration.Local.cscfg`

## <a name="configure-an-azure-cloud-service"></a>Azure 클라우드 서비스를 구성 합니다.
다음 단계에 표시 된 대로 Visual Studio에서 솔루션 탐색기에서 Azure 클라우드 서비스를 구성할 수 있습니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **속성**합니다.
   
    ![솔루션 탐색기 프로젝트 상황에 맞는 메뉴](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-project-context-menu.png)

1. 프로젝트의 속성 페이지에서 선택 합니다 **개발** 탭 합니다. 

    ![프로젝트 속성 페이지-개발 탭](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-development-tab.png)

1. 에 **서비스 구성** 목록에서 편집할 서비스 구성의 이름을 선택 합니다. (이 역할에 대 한 모든 서비스 구성을 변경 하려는 경우 선택 **모든 구성**.)
   
    > [!IMPORTANT]
    > 특정 서비스 구성을 선택 하면 모든 구성에 대해 설정할만 있기 때문에 일부 속성이 비활성화 됩니다. 이러한 속성을 편집 하려면 선택 해야 합니다 **모든 구성**합니다.
    > 
    > 
   
    ![Azure 클라우드 서비스에 대 한 서비스 구성 목록](./media/vs-azure-tools-configure-roles-for-cloud-service/cloud-service-service-configuration-property.png)

## <a name="change-the-number-of-role-instances"></a>역할 인스턴스 수 변경
클라우드 서비스의 성능 향상을 위해 사용자 또는 특정 역할에 대 한 예상 되는 부하의 수에 따라 실행 중인 역할 인스턴스의 수를 변경할 수 있습니다. 클라우드 서비스가 Azure에서 실행 될 때 별도 가상 컴퓨터 역할의 각 인스턴스에 대해 생성 됩니다. 이이 클라우드 서비스의 배포에 대 한 청구를 영향을 줍니다. 청구에 대 한 자세한 내용은 참조 하세요. [Microsoft Azure 청구서 이해](/azure/billing/billing-understand-your-bill)합니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다. 아래는 **역할** 노드를 업데이트 하 고 상황에 맞는 메뉴에서 선택 하려는 역할을 마우스 오른쪽 단추로 클릭 **속성**합니다.

    ![솔루션 탐색기-Azure 역할 상황에 맞는 메뉴](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 선택 된 **구성** 탭 합니다.

    ![구성 탭](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page.png)

1. 에 **서비스 구성** 목록에서 업데이트할 서비스 구성을 선택 합니다.
   
    ![서비스 구성 목록](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page-select-configuration.png)

1. 에 **인스턴스 수** 텍스트 상자에이 역할에 대 한 시작 하려는 인스턴스 수를 입력 합니다. 각 인스턴스는 Azure에 클라우드 서비스를 게시할 때 별도 가상 머신에서 실행 됩니다.

    ![인스턴스 수 업데이트](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page-instance-count.png)

1. Visual Studio에서 도구 모음에서 선택 **저장할**합니다.

## <a name="manage-connection-strings-for-storage-accounts"></a>저장소 계정에 대 한 연결 문자열 관리
추가, 제거 또는 서비스 구성에 대 한 연결 문자열을 수정할 수 있습니다. 값이 있는 로컬 서비스 구성에 대 한 로컬 연결 문자열을 사용할 수 있습니다는 예를 들어, `UseDevelopmentStorage=true`합니다. Azure에서 저장소 계정을 사용 하는 클라우드 서비스 구성을 구성 하려면 수도 있습니다.

> [!WARNING]
> 저장소 계정 연결 문자열에 대 한 Azure storage 계정 키 정보를 입력 하면이 정보는 서비스 구성 파일에 로컬로 저장 됩니다. 그러나이 정보를 암호화 텍스트로 저장 되지 않습니다 현재.
> 
> 

각 서비스 구성에 대 한 다른 값을 사용 하면 클라우드 서비스에서 다른 연결 문자열을 사용 하거나 Azure에 클라우드 서비스를 게시할 때 코드를 수정 하려면 필요가 없습니다. 연결 문자열에 동일한 이름을 사용 하 여 코드의 및 값은 클라우드 서비스를 빌드할 때 또는 게시할 때 선택 하는 서비스 구성에 따라 다릅니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다. 아래는 **역할** 노드를 업데이트 하 고 상황에 맞는 메뉴에서 선택 하려는 역할을 마우스 오른쪽 단추로 클릭 **속성**합니다.

    ![솔루션 탐색기-Azure 역할 상황에 맞는 메뉴](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 선택 된 **설정을** 탭 합니다.

    ![설정 탭](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab.png)

1. 에 **서비스 구성** 목록에서 업데이트할 서비스 구성을 선택 합니다.

    ![서비스 구성](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-select-configuration.png)

1. 연결 문자열을 추가 하려면 **설정 추가**합니다.

    ![연결 문자열 추가](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting.png)

1. 새 설정이 목록에 추가 되 면 필요한 정보를 사용 하 여 목록에서 행을 업데이트 합니다.

    ![새 연결 문자열](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting-new-setting.png)

    - **이름** -연결 문자열에 대 한 사용 하려는 이름을 입력 합니다.
    - **형식** 선택- **연결 문자열** 드롭 다운 목록에서.
    - **값** -연결 문자열을 직접 입력 하거나 합니다 **값** 셀 또는 줄임표 (...)에서 작동 하도록 선택 합니다 **저장소 연결 문자열 만들기** 대화 합니다.  

1. 에 **저장소 연결 문자열 만들기** 대화 상자에서 옵션을 선택 **사용 하 여 연결**합니다. 그런 다음 선택한 옵션에 대 한 지침을 따르세요.

    - **Microsoft Azure storage 에뮬레이터** -Azure에만 적용 되므로 대화 상자의 나머지 설정이 비활성화 됩니다이 옵션을 선택 합니다. **확인**을 선택합니다.
    - **구독의** -이 옵션을 선택 하는 경우 드롭다운 목록을 사용 하 여 중 하나를 선택 하 고 Microsoft 계정에 로그인 하거나 Microsoft 계정을 추가 합니다. Azure 구독 및 저장소 계정을 선택 합니다. **확인**을 선택합니다.
    - **수동으로 입력 한 자격 증명** -저장소 계정 이름과 기본 또는 보조 키를 입력 합니다. 에 대 한 옵션을 선택 **연결** (HTTPS는 대부분의 시나리오에 대 한 것이 좋습니다.) **확인**을 선택합니다.

1. 연결 문자열을 삭제 하려면 연결 문자열을 선택 하 고 선택한 **설정 제거**합니다.

1. Visual Studio에서 도구 모음에서 선택 **저장할**합니다.

## <a name="programmatically-access-a-connection-string"></a>프로그래밍 방식으로 연결 문자열에 액세스

다음 단계를 사용 하 여 연결 문자열을 프로그래밍 방식으로 액세스 하는 방법을 보여 줍니다 C#입니다.

1. 다음 추가 지시문을 사용 하는 C# 설정을 사용 하려는 파일:

    ```csharp
    using Microsoft.WindowsAzure;
    using Microsoft.WindowsAzure.Storage;
    using Microsoft.WindowsAzure.ServiceRuntime;
    ```

1. 다음 코드에서는 연결 문자열에 액세스 하는 방법의 예제를 보여 줍니다. 대체는 &lt;ConnectionStringName > 자리 표시자를 적절 한 값을 변경 합니다. 

    ```csharp
    // Setup the connection to Azure Storage
    var storageAccount = CloudStorageAccount.Parse(RoleEnvironment.GetConfigurationSettingValue("<ConnectionStringName>"));
    ```

## <a name="add-custom-settings-to-use-in-your-azure-cloud-service"></a>Azure 클라우드 서비스에서 사용할 사용자 지정 설정 추가
서비스 구성 파일에서 사용자 지정 설정 이름 및 특정 서비스 구성에 대 한 문자열 값을 추가할 수 있습니다. 설정의 값을 읽고이 값을 사용 하 여 코드의 논리를 제어 하 여 클라우드 서비스의 기능을 구성 하려면이 설정을 사용 하도록 선택할 수 있습니다. 클라우드 서비스가 실행 되는 경우 또는 서비스 패키지를 다시 빌드하지 않고도 이러한 서비스 구성 값을 변경할 수 있습니다. 설정은 변경 될 때 코드에 대 한 알림을 확인할 수 있습니다. 참조 [RoleEnvironment.Changing 이벤트](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleenvironment.changing.aspx)합니다.

추가, 제거 또는 서비스 구성에 대 한 사용자 지정 설정을 수정할 수 있습니다. 다양 한 서비스 구성에 대해 이러한 문자열에 대 한 값이 다른 경우가 있습니다.

각 서비스 구성에 대 한 다른 값을 사용 하면 클라우드 서비스에서 다른 문자열을 사용 하거나 Azure에 클라우드 서비스를 게시할 때 코드를 수정 하려면 필요가 없습니다. 문자열에 동일한 이름을 사용 하 여 코드의 및 값은 클라우드 서비스를 빌드할 때 또는 게시할 때 선택 하는 서비스 구성에 따라 다릅니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다. 아래는 **역할** 노드를 업데이트 하 고 상황에 맞는 메뉴에서 선택 하려는 역할을 마우스 오른쪽 단추로 클릭 **속성**합니다.

    ![솔루션 탐색기-Azure 역할 상황에 맞는 메뉴](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 선택 된 **설정을** 탭 합니다.

    ![설정 탭](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab.png)

1. 에 **서비스 구성** 목록에서 업데이트할 서비스 구성을 선택 합니다.

    ![서비스 구성 목록](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-select-configuration.png)

1. 사용자 지정 설정을 추가 하려면 **설정 추가**합니다.

    ![사용자 지정 설정 추가](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting.png)

1. 새 설정이 목록에 추가 되 면 필요한 정보를 사용 하 여 목록에서 행을 업데이트 합니다.

    ![새 사용자 지정 설정](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting-new-setting.png)

    - **이름** -설정의 이름을 입력 합니다.
    - **형식** 선택- **문자열** 드롭 다운 목록에서.
    - **값** -설정의 값을 입력 합니다. 값을 직접 입력 하거나 합니다 **값** 셀 또는 값을 입력 하려면 줄임표 (...)를 선택 합니다 **문자열 편집** 대화 합니다.  

1. 사용자 지정 설정을 삭제를 선택 하 고 설정을 선택한 후 **설정 제거**합니다.

1. Visual Studio에서 도구 모음에서 선택 **저장할**합니다.

## <a name="programmatically-access-a-custom-settings-value"></a>프로그래밍 방식으로 사용자 지정 설정의 값에 액세스
 
다음 단계를 사용 하 여 사용자 지정 설정을 프로그래밍 방식으로 액세스 하는 방법을 보여 줍니다 C#입니다.

1. 다음 추가 지시문을 사용 하는 C# 설정을 사용 하려는 파일:

    ```csharp
    using Microsoft.WindowsAzure;
    using Microsoft.WindowsAzure.Storage;
    using Microsoft.WindowsAzure.ServiceRuntime;
    ```

1. 다음 코드에서는 사용자 지정 설정에 액세스 하는 방법의 예제를 보여 줍니다. 대체는 &lt;SettingName > 자리 표시자를 적절 한 값을 변경 합니다. 
    
    ```csharp
    var settingValue = RoleEnvironment.GetConfigurationSettingValue("<SettingName>");
    ```

## <a name="manage-local-storage-for-each-role-instance"></a>각 역할 인스턴스에 대 한 로컬 저장소를 관리 합니다.
역할의 각 인스턴스에 대 한 로컬 파일 시스템 저장소를 추가할 수 있습니다. 또는 다른 역할의 데이터를 저장 하는 역할의 다른 인스턴스에서 액세스할 수 없는 저장소에 저장 된 데이터.  

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다. 아래는 **역할** 노드를 업데이트 하 고 상황에 맞는 메뉴에서 선택 하려는 역할을 마우스 오른쪽 단추로 클릭 **속성**합니다.

    ![솔루션 탐색기-Azure 역할 상황에 맞는 메뉴](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 선택 된 **로컬 저장소** 탭 합니다.

    ![로컬 저장소 탭](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab.png)

1. 에 **서비스 구성을** 목록에서 **모든 구성** 모든 서비스 구성에 로컬 저장소 설정이 적용을 선택 합니다. 사용 하지 않도록 설정 되 고 페이지의 모든 입력된 필드에 다른 값이 발생 합니다. 

    ![서비스 구성 목록](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-service-configuration.png)

1. 로컬 저장소 항목을 추가 하려면 **로컬 저장소 추가**합니다.

    ![로컬 저장소 추가](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-add-local-storage.png)

1. 새 로컬 저장소 항목 목록에 추가한 후 필요한 정보를 사용 하 여 목록에서 행을 업데이트 합니다.

    ![새 로컬 저장소 항목](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-new-local-storage.png)

    - **이름** -새 로컬 저장소에 사용 하려는 이름을 입력 합니다.
    - **크기 (MB)** -새 로컬 저장소에 필요한 MB 단위로 크기를 입력 합니다.
    - **역할 재생에서 정리** -가상 컴퓨터 역할에 대 한 재활용 될 때 새 로컬 저장소에서 데이터를 제거 하려면이 옵션을 선택 합니다.

1. 로컬 저장소 항목을 삭제 하려면 항목을 선택 하 고 선택한 **로컬 저장소 제거**합니다.

1. Visual Studio에서 도구 모음에서 선택 **저장할**합니다.

## <a name="programmatically-accessing-local-storage"></a>프로그래밍 방식으로 로컬 저장소에 액세스

이 섹션에서는 프로그래밍 방식으로 사용 하 여 로컬 저장소를 액세스 하는 방법을 보여 줍니다. C# 테스트 텍스트 파일을 작성 하 여 `MyLocalStorageTest.txt`합니다.  

### <a name="write-a-text-file-to-local-storage"></a>로컬 저장소에 텍스트 파일 쓰기

다음 코드에는 로컬 저장소에 텍스트 파일을 작성 하는 방법의 예가 나와 있습니다. 대체는 &lt;LocalStorageName > 자리 표시자를 적절 한 값을 변경 합니다. 

    ```csharp
    // Retrieve an object that points to the local storage resource
    LocalResource localResource = RoleEnvironment.GetLocalResource("<LocalStorageName>");
    
    //Define the file name and path
    string[] paths = { localResource.RootPath, "MyLocalStorageTest.txt" };
    String filePath = Path.Combine(paths);
    
    using (FileStream writeStream = File.Create(filePath))
    {
        Byte[] textToWrite = new UTF8Encoding(true).GetBytes("Testing Web role storage");
        writeStream.Write(textToWrite, 0, textToWrite.Length);
    }

    ```

### <a name="find-a-file-written-to-local-storage"></a>로컬 저장소에 기록 된 파일 찾기

이전 섹션의 코드에서 만든 파일을 보려면 다음을 수행 합니다.
    
1.  Windows 알림 영역에서 Azure 아이콘을 마우스 오른쪽 단추로 클릭 하 고, 상황에 맞는 메뉴에서 선택 **Compute 에뮬레이터 UI 표시**합니다. 

    ![Azure 컴퓨팅 에뮬레이터 표시](./media/vs-azure-tools-configure-roles-for-cloud-service/show-compute-emulator.png)

1. 웹 역할을 선택 합니다.

    ![Azure 컴퓨팅 에뮬레이터](./media/vs-azure-tools-configure-roles-for-cloud-service/compute-emulator.png)

1. 에 **Microsoft Azure Compute 에뮬레이터** 메뉴에서 **도구** > **로컬 저장소 열기**합니다.

    ![로컬 저장소 열기 메뉴 항목](./media/vs-azure-tools-configure-roles-for-cloud-service/compute-emulator-open-local-store-menu.png)

1. Windows 탐색기 창이 열리면 입력 ' MyLocalStorageTest.txt '에 **검색** 텍스트 상자에서 선택한 **Enter** 검색을 시작 합니다. 

## <a name="next-steps"></a>다음 단계
에 대해 자세히 알아보려면 Visual Studio에서 Azure 프로젝트를 읽으면 [Azure 프로젝트 구성](vs-azure-tools-configuring-an-azure-project.md)합니다. 에 대해 자세히 알아보려면 클라우드 서비스 스키마를 읽으면 [스키마 참조](https://msdn.microsoft.com/library/azure/dd179398)합니다.

