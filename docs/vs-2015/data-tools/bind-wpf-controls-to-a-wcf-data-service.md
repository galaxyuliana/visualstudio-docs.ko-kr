---
title: WCF 데이터 서비스에 WPF 컨트롤 바인딩 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 8823537c-82f0-41f7-bf30-705f0e5e59fd
caps.latest.revision: 44
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fb08a016261ac0836ba6dd2dde5d8b0812aab806
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704912"
---
# <a name="bind-wpf-controls-to-a-wcf-data-service"></a>WCF 데이터 서비스에 WPF 컨트롤 바인딩
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 데이터 바인딩된 컨트롤을 포함하는 WPF 애플리케이션을 만듭니다. 이러한 컨트롤은 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]에서 캡슐화된 고객 레코드에 바인딩됩니다. 또한 고객이 레코드를 보고 업데이트하는 데 사용할 수 있는 단추도 추가합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
- AdventureWorksLT 샘플 데이터베이스의 데이터에서 생성되는 엔터티 데이터 모델을 만듭니다.  
  
- 만들기는 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] WPF 응용 프로그램 엔터티 데이터 모델의 데이터를 노출 합니다.  
  
- **데이터 원본** 창에서 WPF 디자이너로 항목을 끌어 데이터 바인딩된 컨트롤 집합을 만듭니다.  
  
- 고객 레코드를 앞뒤로 탐색하는 데 사용할 단추를 만듭니다.  
  
- 컨트롤의 데이터 변경 내용을 저장 하는 단추 만들기는 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] 및 기본 데이터 원본입니다.  
  
   [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
- [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]  
  
- AdventureWorksLT 샘플 데이터베이스가 연결된 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스 액세스 권한. AdventureWorksLT 데이터베이스를 다운로드할 수 있습니다 합니다 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)합니다.  
  
  또한 다음 개념에 대한 지식은 연습을 완료하는 데 반드시 필요하지는 않지만 사전에 파악해 두면 유용할 수 있습니다.  
  
- WCF Data Services. 자세한 내용은 [개요](https://msdn.microsoft.com/library/7924cf94-c9a6-4015-afc9-f5d22b1743bb)합니다.  
  
- [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)]의 데이터 모델  
  
- 엔터티 데이터 모델 및 ADO.NET Entity Framework 자세한 내용은 [Entity Framework 개요](https://msdn.microsoft.com/library/a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0)합니다.  
  
- WPF 디자이너 사용법. 자세한 내용은 [WPF 및 Silverlight 디자이너 개요](https://msdn.microsoft.com/570b7a5c-0c86-4326-a371-c9b63378fc62)합니다.  
  
- WPF 데이터 바인딩. 자세한 내용은 [데이터 바인딩 개요](https://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)를 참조하세요.  
  
## <a name="create-the-service-project"></a>서비스 프로젝트를 만들려면  
 이 연습에서는 먼저 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]용 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-service-project"></a>해당 서비스 프로젝트를 만들려면  
  
1. Visual Studio를 시작합니다.  
  
2. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3. **Visual C#** 또는 **Visual Basic**을 확장한 다음, **웹**을 선택합니다.  
  
4. **ASP.NET 웹 응용 프로그램** 프로젝트 템플릿을 선택합니다.  
  
5. 에 **이름을** 상자에 입력 `AdventureWorksService` 클릭 **확인**합니다.  
  
     Visual Studio 만듭니다는 `AdventureWorksService` 프로젝트입니다.  
  
6. **솔루션 탐색기**에서 **Default.aspx**를 오른쪽 마우스 단추로 클릭하고 **삭제**를 선택합니다. 이 연습에서는 해당 파일이 필요하지 않습니다.  
  
## <a name="create-an-entity-data-model-for-the-service"></a>서비스에 대 한 엔터티 데이터 모델 만들기  
 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]를 사용하여 애플리케이션에 데이터를 표시하려면 서비스에 대해 데이터 모델을 정의해야 합니다. [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] 두 가지 유형의 데이터 모델을 지원 합니다. 엔터티 데이터 모델 및 구현 하는 공용 언어 런타임 (CLR) 개체를 사용 하 여 정의 된 사용자 지정 데이터 모델을 <xref:System.Linq.IQueryable%601> 인터페이스입니다. 이 연습에서는 데이터 모델에 대해 엔터티 데이터 모델을 만듭니다.  
  
#### <a name="to-create-an-entity-data-model"></a>엔터티 데이터 모델을 만들려면  
  
1. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2. 설치된 템플릿 목록에서 **데이터**를 클릭한 다음, **ADO.NET 엔터티 데이터 모델** 프로젝트 항목을 선택합니다.  
  
3. 이름을 변경할 `AdventureWorksModel.edmx`, 클릭 **추가**합니다.  
  
     **엔터티 데이터 모델** 마법사가 열립니다.  
  
4. **모델 콘텐츠 선택** 페이지에서 **데이터베이스에서 생성**을 클릭한 후, **다음**을 클릭합니다.  
  
5. **데이터 연결 선택** 페이지에서 다음 옵션 중 하나를 선택합니다.  
  
    - AdventureWorksLT 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
    - **새 연결**을 클릭하고 AdventureWorksLT 데이터베이스에 대한 연결을 만듭니다.  
  
6. **데이터 연결 선택** 페이지에서 **다른 이름으로 App.Config의 엔터티 연결 설정 저장** 옵션이 선택되어 있는지 확인한 후, **다음**을 클릭합니다.  
  
7. **데이터베이스 개체 선택** 페이지에서 **테이블**을 확장한 다음, **SalesOrderHeader** 테이블을 선택합니다.  
  
8. **마침**을 클릭합니다.  
  
## <a name="create-the-service"></a>서비스 만들기  
 만들기는 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] WPF 응용 프로그램 엔터티 데이터 모델에서 데이터를 노출 합니다.  
  
#### <a name="to-create-the-service"></a>해당 서비스를 만들려면  
  
1. **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
2. 설치 된 템플릿 목록에서 클릭 **웹**를 선택한 후 합니다 **WCF 데이터 서비스** 프로젝트 항목입니다.  
  
3. 에 **이름을** 상자에 입력 `AdventureWorksService.svc`, 클릭 **추가**합니다.  
  
     Visual Studio에 추가 된 `AdventureWorksService.svc` 프로젝트에.  
  
## <a name="configure-the-service"></a>서비스 구성  
 작성한 엔터티 데이터 모델에 대해 작동하도록 서비스를 구성해야 합니다.  
  
#### <a name="to-configure-the-service"></a>서비스를 구성하려면  
  
1. 에 `AdventureWorks.svc` 코드 파일에서 바꾸기는 `AdventureWorksService` 클래스 선언을 다음 코드로 합니다.  
  
     [!code-csharp[Data_WPFWCF#1](../snippets/csharp/VS_Snippets_ProTools/data_wpfwcf/cs/adventureworksservice.svc.cs#1)]
     [!code-vb[Data_WPFWCF#1](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfwcf/vb/adventureworksservice.svc.vb#1)]  
  
     이 코드는 업데이트를 `AdventureWorksService` 에서 파생 되도록 클래스를 <xref:System.Data.Services.DataService%601> 에서 작동 하는 `AdventureWorksLTEntities` 개체 컨텍스트 클래스 엔터티 데이터 모델에 합니다. 또한 서비스의 클라이언트에 `InitializeService` 엔터티에 대한 모든 읽기/쓰기 권한을 허용하도록 `SalesOrderHeader` 메서드를 업데이트합니다.  
  
2. 프로젝트를 빌드하고 오류가 없이 빌드되는지 확인합니다.  
  
## <a name="create-the-wpf-client-application"></a>WPF 클라이언트 응용 프로그램 만들기  
 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]에서 데이터를 표시하려면 서비스를 기반으로 하는 데이터 소스를 사용하여 새 WPF 애플리케이션을 만듭니다. 이 연습 뒷부분에서 애플리케이션에 데이터 바인딩된 컨트롤을 추가합니다.  
  
#### <a name="to-create-the-wpf-client-application"></a>WPF 클라이언트 애플리케이션을 만들려면  
  
1. **솔루션 탐색기**에서 솔루션 노드를 마우스 오른쪽 단추로 클릭하고, **추가**를 클릭하고, **새 프로젝트**를 선택합니다.  
  
2. **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic**을 확장한 다음, **Windows**를 선택합니다.  
  
3. **WPF 애플리케이션** 프로젝트 템플릿을 선택합니다.  
  
4. **이름** 상자에 `AdventureWorksSalesEditor`를 입력하고 **확인**을 클릭합니다.  
  
     Visual Studio에 추가 된 `AdventureWorksSalesEditor` 프로젝트를 솔루션입니다.  
  
5. **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
     **데이터 원본** 창이 열립니다.  
  
6. **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     **데이터 원본 구성** 마법사가 열립니다.  
  
7. 마법사의 **데이터 원본 형식 선택** 페이지에서 **서비스**를 선택한 후, **다음**을 클릭합니다.  
  
8. **서비스 참조 추가** 대화 상자에서 **검색**을 클릭합니다.  
  
     Visual Studio는 사용 가능한 서비스에 대 한 현재 솔루션을 검색 하 고 추가 `AdventureWorksService.svc` 에서 사용 가능한 서비스 목록에는 **Services** 상자입니다.  
  
9. 에 **Namespace** 상자에 입력 `AdventureWorksService`합니다.  
  
10. **서비스** 상자에서 **AdventureWorksService.svc**를 클릭한 다음, **확인**을 클릭합니다.  
  
     Visual Studio 서비스 정보를 다운로드 하 고 다음을 반환 합니다 **데이터 원본 구성** 마법사.  
  
11. **서비스 참조 추가** 페이지에서 **마침**을 클릭합니다.  
  
     Visual Studio는 서비스에서 반환하는 데이터를 나타내는 노드를 **데이터 원본** 창에 추가합니다.  
  
## <a name="define-the-user-interface-of-the-window"></a>창의 사용자 인터페이스를 정의 합니다.  
 WPF 디자이너에서 XAML을 수정하여 창에 여러 단추를 추가합니다. 이 연습 뒷부분에서 사용자가 이러한 단추를 사용해 판매 레코드를 보고 업데이트할 수 있도록 하는 코드를 추가합니다.  
  
#### <a name="to-create-the-window-layout"></a>창 레이아웃을 만들려면  
  
1. **솔루션 탐색기**에서 MainWindow.xaml을 두 번 클릭 합니다.  
  
     WPF 디자이너에서 창이 열립니다.  
  
2. 디자이너의 [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] 뷰에서 `<Grid>` 태그 사이에 다음 코드를 추가합니다.  
  
    ```  
    <Grid.RowDefinitions>  
        <RowDefinition Height="75" />  
        <RowDefinition Height="525" />  
    </Grid.RowDefinitions>  
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>  
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>  
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>  
    ```  
  
3. 프로젝트를 빌드합니다.  
  
## <a name="create-the-data-bound-controls"></a>데이터 바인딩된 컨트롤 만들기  
 끌어 고객 레코드를 표시 하는 컨트롤을 만들 합니다 `SalesOrderHeaders` 에서 노드를 **데이터 원본** 창에서 디자이너로 합니다.  
  
#### <a name="to-create-the-data-bound-controls"></a>데이터 바인딩된 컨트롤을 만들려면  
  
1. **데이터 원본** 창에서 **SalesOrderHeaders** 노드의 드롭다운 메뉴를 클릭하고 **정보**를 선택합니다.  
  
2. **SalesOrderHeaders** 노드를 확장합니다.  
  
3. 이 예에서는 일부 필드를 표시하지 않을 것이므로 다음 노드 옆의 드롭다운 메뉴를 클릭하고 **없음**을 선택합니다.  
  
   - **CreditCardApprovalCode**  
  
   - **ModifiedDate**  
  
   - **OnlineOrderFlag**  
  
   - **RevisionNumber**  
  
   - **rowguid**  
  
     이 작업을 수행하면 다음 단계에서 이러한 노드에 대해 데이터 바인딩된 컨트롤이 작성되지 않습니다. 이 연습에서는 최종 사용자는이 데이터를 볼 필요가 없습니다를 가정 합니다.  
  
4. **데이터 원본** 창에서 단추가 포함된 행 아래의 데이터 그리드 행으로 **SalesOrderHeaders** 노드를 끌어 옵니다.  
  
    Visual Studio는 **Product** 테이블의 데이터에 바인딩되는 컨트롤 집합을 만드는 XAML 및 코드를 생성합니다. 생성 된 XAML 및 코드에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 데이터를 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)합니다.  
  
5. 디자이너에서 **고객 ID** 레이블 옆의 텍스트 상자를 클릭합니다.  
  
6. **속성** 창에서 **IsReadOnly** 속성 옆의 확인란을 선택합니다.  
  
7. 다음의 각 텍스트 상자에 대해 **IsReadOnly** 속성을 설정합니다.  
  
   - **구매 주문 번호**  
  
   - **판매 주문 ID**  
  
   - **판매 주문 번호**  
  
## <a name="load-the-data-from-the-service"></a>서비스에서 데이터 로드  
 서비스 프록시 개체를 사용 하 여 서비스에서 판매 데이터를 로드 합니다. 그런 다음 반환된 된 데이터에 대 한 데이터 원본에 할당 된 <xref:System.Windows.Data.CollectionViewSource> WPF 창에서.  
  
#### <a name="to-load-the-data-from-the-service"></a>서비스에서 데이터를 로드하려면  
  
1. 디자이너를 만들려면를 `Window_Loaded` 이벤트 처리기에서 텍스트를 두 번 클릭: **MainWindow**합니다.  
  
2. 이벤트 처리기를 다음 코드로 바꿉니다. 이 코드의 *localhost*주소는 사용 중인 개발 컴퓨터의 로컬 호스트 주소로 바꿔야 합니다.  
  
     [!code-csharp[Data_WPFWCF#2](../snippets/csharp/VS_Snippets_ProTools/data_wpfwcf/cs/adventureworkssaleseditor/mainwindow.xaml.cs#2)]
     [!code-vb[Data_WPFWCF#2](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfwcf/vb/adventureworkssaleseditor/mainwindow.xaml.vb#2)]  
  
## <a name="navigatesales-records"></a>Navigatesales 레코드  
 사용자가 **\<** 및 **>** 단추를 사용하여 판매 레코드를 스크롤할 수 있도록 하는 코드를 추가합니다.  
  
#### <a name="to-enable-users-to-navigate-sales-records"></a>사용자가 판매 레코드를 탐색할 수 있도록 설정하려면  
  
1. 디자이너의 창 화면에서 **<** 단추를 두 번 클릭합니다.  
  
     Visual Studio가 코드 숨김 파일을 열고 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대해 새 `backButton_Click` 이벤트 처리기를 만듭니다.  
  
2. 다음 코드를 생성된 `backButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFWCF#3](../snippets/csharp/VS_Snippets_ProTools/data_wpfwcf/cs/adventureworkssaleseditor/mainwindow.xaml.cs#3)]
     [!code-vb[Data_WPFWCF#3](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfwcf/vb/adventureworkssaleseditor/mainwindow.xaml.vb#3)]  
  
3. 디자이너로 돌아와서 **>** 단추를 두 번 클릭합니다.  
  
     Visual Studio가 코드 숨김 파일을 열고 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대해 새 `nextButton_Click` 이벤트 처리기를 만듭니다.  
  
4. 다음 코드를 생성된 `nextButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFWCF#4](../snippets/csharp/VS_Snippets_ProTools/data_wpfwcf/cs/adventureworkssaleseditor/mainwindow.xaml.cs#4)]
     [!code-vb[Data_WPFWCF#4](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfwcf/vb/adventureworkssaleseditor/mainwindow.xaml.vb#4)]  
  
## <a name="saving-changes-to-sales-records"></a>판매 레코드 변경 내용 저장  
 보기를 사용 하 여 판매 레코드 변경 내용을 저장할 수 있게 해 주는 코드를 추가 합니다 **변경 내용을 저장** 단추입니다.  
  
#### <a name="to-add-the-ability-to-save-changes-to-sales-records"></a>판매 레코드 변경 내용을 저장하는 기능을 추가하려면  
  
1. 디자이너에서 **변경 내용 저장** 단추를 두 번 클릭합니다.  
  
     Visual Studio가 코드 숨김 파일을 열고 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대해 새 `saveButton_Click` 이벤트 처리기를 만듭니다.  
  
2. 다음 코드를 `saveButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFWCF#5](../snippets/csharp/VS_Snippets_ProTools/data_wpfwcf/cs/adventureworkssaleseditor/mainwindow.xaml.cs#5)]
     [!code-vb[Data_WPFWCF#5](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfwcf/vb/adventureworkssaleseditor/mainwindow.xaml.vb#5)]  
  
## <a name="testing-the-application"></a>애플리케이션 테스트  
 애플리케이션을 빌드하고 실행하여 고객 레코드를 보고 업데이트할 수 있는지 확인합니다.  
  
#### <a name="to-test-the-application"></a>애플리케이션을 테스트하려면  
  
1. **빌드합니다** 메뉴에서 클릭 **솔루션 빌드**합니다. 솔루션이 오류 없이 빌드되는지 확인합니다.  
  
2. 키를 눌러 **ctrl+f5**합니다.  
  
     Visual Studio는 디버깅하지 않고 **AdventureWorksService** 프로젝트를 시작합니다.  
  
3. **솔루션 탐색기**에서 **AdventureWorksSalesEditor** 프로젝트를 마우스 오른쪽 단추로 클릭합니다.  
  
4. 컨텍스트 메뉴의 **디버그**에서 **새 인스턴스 시작**을 클릭합니다.  
  
     애플리케이션이 실행됩니다. 다음 사항을 확인합니다.  
  
    - 판매 주문 ID가 **71774**인 첫 번째 판매 레코드의 서로 다른 데이터 필드가 텍스트 상자에 표시됩니다.  
  
    - **>** 또는 **<** 단추를 클릭하여 다른 판매 레코드를 탐색할 수 있습니다.  
  
5. 판매 레코드 중 하나의 **주석** 상자에 텍스트를 입력한 다음, **변경내용 저장**을 클릭합니다.  
  
6. 애플리케이션을 닫았다가 Visual Studio에서 다시 시작합니다.  
  
7. 변경한 판매 레코드로 이동하여 애플리케이션을 닫았다가 다시 열어도 변경 내용이 그대로 유지되는지 확인합니다.  
  
8. 애플리케이션을 닫습니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습을 완료하고 나면 다음과 같은 관련 작업을 수행할 수 있습니다.  
  
- Visual Studio의 **데이터 원본** 창을 사용하여 WPF 컨트롤을 다른 형식의 데이터 원본에 바인딩하는 방법을 알아봅니다. 자세한 내용은 [데이터 집합에 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-a-dataset.md)합니다.  
  
- Visual Studio의 **데이터 원본** 창을 사용하여 WPF 컨트롤에 관련 데이터(즉, 부모-자식 관계가 있는 데이터)를 표시하는 방법을 알아봅니다. 자세한 내용은 [연습: WPF 응용 프로그램에서 관련된 데이터 표시](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)   
 [데이터 집합에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-dataset.md)   
 [개요](https://msdn.microsoft.com/library/7924cf94-c9a6-4015-afc9-f5d22b1743bb)   
 [Entity Framework 개요](https://msdn.microsoft.com/library/a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0)   
 [WPF 및 Silverlight 디자이너 개요](https://msdn.microsoft.com/570b7a5c-0c86-4326-a371-c9b63378fc62)   
 [데이터 바인딩 개요](https://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)
