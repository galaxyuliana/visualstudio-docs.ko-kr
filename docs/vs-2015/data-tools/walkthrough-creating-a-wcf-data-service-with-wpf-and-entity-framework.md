---
title: '연습: WPF 및 Entity Framework를 사용 하 여 WCF 데이터 서비스 만들기 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
caps.latest.revision: 28
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 12d7e9c25cdf4e0431a7e4b5e3639dc59b76790c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703170"
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>연습: WPF 및 Entity Framework를 사용하여 WCF 데이터 서비스 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에는 간단한을 만드는 방법을 보여 줍니다 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] 에서 호스팅되는 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 웹 응용 프로그램 및 Windows Forms 응용 프로그램에서 액세스 합니다.  
  
 이 연습에서는 다음과 같은 작업을 수행합니다.  
  
- [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]를 호스팅하는 웹 애플리케이션을 만듭니다.  
  
- Northwind 데이터베이스의 Customers 테이블을 나타내는 [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]을 만듭니다.  
  
- [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]를 만듭니다.  
  
- 클라이언트 애플리케이션을 만들고 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]에 대한 참조를 추가합니다.  
  
- 서비스에 대한 데이터 바인딩을 활성화하고 사용자 인터페이스를 생성합니다.  
  
- 필요한 경우 애플리케이션에 필터링 기능을 추가합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
- Northwind 샘플 데이터베이스  
  
     이 데이터베이스가 개발 컴퓨터에 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088)에서 다운로드할 수 있습니다. 자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/ef9d69a1-9461-43fe-94bb-7c836754bcb5)합니다.  
  
## <a name="creating-the-service"></a>서비스 만들기  
 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]를 만들려면 웹 프로젝트를 추가하고 [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]을 만든 다음 이 모델에서 서비스를 만듭니다.  
  
 첫 번째 단계에서는 서비스를 호스팅할 웹 프로젝트를 추가합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-the-web-project"></a>웹 프로젝트를 만들려면  
  
1. 메뉴 모음에서 **파일**, **새로 만들기**하십시오 **프로젝트**.  
  
2. **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#** 및 **웹** 노드를 확장한 다음, **ASP.NET 웹 애플리케이션** 템플릿을 선택합니다.  
  
3. **이름** 텍스트 상자에 **NorthwindWeb**을 입력한 다음, **확인** 단추를 선택합니다.  
  
4. **새 ASP.NET 프로젝트** 대화 상자의 **템플릿 선택** 목록에서 **비어 있음**을 선택한 다음, **확인** 단추를 선택합니다.  
  
   이 단계에서는 Northwind 데이터베이스의 Customers 테이블을 나타내는 [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]을 만듭니다.  
  
#### <a name="to-create-the-entity-data-model"></a>엔터티 데이터 모델을 만들려면  
  
1. 메뉴 모음에서 선택 **프로젝트**하십시오 **새 항목 추가**합니다.  
  
2. **새 항목 추가** 대화 상자에서 **데이터** 노드를 선택한 다음, **ADO.NET 엔터티 데이터 모델** 항목을 선택합니다.  
  
3. 에 **이름** 텍스트 상자에 입력 합니다 `NorthwindModel`를 선택한 후는 **추가** 단추입니다.  
  
    엔터티 데이터 모델 마법사가 나타납니다.  
  
4. 엔터티 데이터 모델 마법사의 **모델 콘텐츠 선택** 페이지에서 **데이터베이스의 EF 디자이너** 항목을 선택한 후, **다음** 단추를 선택합니다.  
  
5. **데이터 연결 선택** 페이지에서 다음 단계 중 하나를 수행합니다.  
  
   - Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
        또는  
  
   - **새 연결** 단추를 선택하여 새 데이터 연결을 구성합니다. 자세한 내용은 [새 연결 추가](../data-tools/add-new-connections.md)합니다.  
  
6. 데이터베이스에 암호가 필요한 경우 **예, 중요한 데이터를 연결 문자열에 포함합니다.** 옵션 단추를 선택한 후, **다음** 단추를 선택합니다.  
  
   > [!NOTE]
   > 대화 상자가 나타나는 경우 **예**를 선택하여 프로젝트에 파일을 저장합니다.  
  
7. **사용자 버전 선택** 페이지에서 **Entity Framework 5.0** 옵션 단추를 선택한 후, **다음** 단추를 선택합니다.  
  
   > [!NOTE]
   > 최신 버전의 Entity Framework 6을 WCF Services와 함께 사용하려면 WCF Data Services Entity Framework Provider NuGet 패키지를 설치해야 합니다. 참조 [WCF 데이터를 사용 하 여 Entity Framework 6을 사용 하 여 5.6.0 Services](http://blogs.msdn.com/b/odatateam/archive/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6.aspx)합니다.  
  
8. **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장하고 **Customers** 확인란을 선택한 다음, **마침** 단추를 선택합니다.  
  
    엔터티 모델 다이어그램이 표시되고 NorthwindModel.edmx 파일이 프로젝트에 추가됩니다.  
  
   이 단계에서는 데이터 서비스를 만들고 테스트합니다.  
  
#### <a name="to-create-the-data-service"></a>데이터 서비스를 만들려면  
  
1. 메뉴 모음에서 선택 **프로젝트**하십시오 **새 항목 추가**합니다.  
  
2. **새 항목 추가** 대화 상자에서 **웹** 노드를 선택한 다음, **WCF Data Service 5.6** 항목을 선택합니다.  
  
3. 에 **이름** 텍스트 상자에 입력 합니다 `NorthwindCustomers`를 선택한 후는 **추가** 단추입니다.  
  
    NorthwindCustomers.svc 파일이 표시 되는 **코드 편집기**합니다.  
  
4. **코드 편집기**에서 첫 번째 `TODO:` 주석을 찾아 다음 코드로 바꿉니다.  
  
    [!code-csharp[WCFDataServiceWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/cs/northwindcustomers.svc.cs#1)]
    [!code-vb[WCFDataServiceWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/vb/northwindcustomers.svc.vb#1)]  
  
5. `InitializeService` 이벤트 처리기의 주석을 다음 코드로 바꿉니다.  
  
    [!code-csharp[WCFDataServiceWalkthrough#2](../snippets/csharp/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/cs/northwindcustomers.svc.cs#2)]
    [!code-vb[WCFDataServiceWalkthrough#2](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/vb/northwindcustomers.svc.vb#2)]  
  
6. 메뉴 모음에서 선택 **디버그**를 **디버깅 하지 않고 시작** 서비스를 실행 합니다. 브라우저 창이 열리고 서비스에 대한 XML 스키마가 표시됩니다.  
  
7. 에 **주소** 막대에서 입력 `Customers` NorthwindCustomers.svc에 대 한 URL의 끝에 선택한 후는 **ENTER** 키입니다.  
  
    Customers 테이블에 있는 데이터의 XML 표현이 표시됩니다.  
  
   > [!NOTE]
   > Internet Explorer가 이 데이터를 RSS 피드로 잘못 해석하는 경우도 있습니다. RSS 피드를 표시하는 옵션은 반드시 비활성화되어 있어야 합니다. 자세한 내용은 [서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)합니다.  
  
8. 브라우저 창을 닫습니다.  
  
   다음 단계에서는 서비스를 소비할 Windows Forms 클라이언트 애플리케이션을 만듭니다.  
  
## <a name="creating-the-client-application"></a>클라이언트 애플리케이션 만들기  
 클라이언트 애플리케이션을 만들려면 두 번째 프로젝트를 추가하고, 프로젝트에 서비스 참조를 추가하고, 데이터 소스를 구성하고, 서비스의 데이터를 표시할 사용자 인터페이스를 만듭니다.  
  
 첫 번째 단계에서는 Windows Forms 프로젝트를 솔루션에 추가한 다음 이를 시작 프로젝트로 설정합니다.  
  
#### <a name="to-create-the-client-application"></a>클라이언트 애플리케이션을 만들려면  
  
1. 메뉴 모음에서 파일을 선택 **추가**하십시오 **새 프로젝트**합니다.  
  
2. 에 **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#** 노드 선택 합니다 **Windows** 노드를를 선택한 다음  **Windows Forms 응용 프로그램**합니다.  
  
3. **이름** 텍스트 상자에 `NorthwindClient`를 입력하고 **확인** 단추를 선택합니다.  
  
4. **솔루션 탐색기**에서 **NorthwindClient** 프로젝트 노드를 선택합니다.  
  
5. 메뉴 모음에서 **프로젝트**, **시작 프로젝트로 설정**을 차례로 선택합니다.  
  
   이 단계에서는 웹 프로젝트에서 [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)]에 대한 서비스 참조를 추가합니다.  
  
#### <a name="to-add-a-service-reference"></a>서비스 참조를 추가하려면  
  
1. 메뉴 모음에서 선택 **프로젝트**하십시오 **서비스 참조 추가**합니다.  
  
2. **서비스 참조 추가** 대화 상자에서 **검색** 단추를 선택합니다.  
  
    NorthwindCustomers 서비스의 URL이 **주소** 필드에 표시됩니다.  
  
3. **확인** 단추를 선택하여 서비스 참조를 추가합니다.  
  
   이 단계에서는 서비스에 대한 데이터 바인딩을 사용하도록 데이터 소스를 구성합니다.  
  
#### <a name="to-enable-data-binding-to-the-service"></a>서비스에 대한 데이터 바인딩을 사용하려면  
  
1. 메뉴 모음에서 선택 **뷰**, **기타 Windows**를 **데이터 원본**합니다.  
  
2. **데이터 원본** 창에서 **새 데이터 원본 추가** 단추를 선택합니다.  
  
3. **데이터 원본 구성 마법사**의 **데이터 소스 형식 선택** 페이지에서 **개체**를 선택한 후, **다음** 단추를 선택합니다.  
  
4. **데이터 개체 선택** 페이지에서 **NorthwindClient** 노드를 확장한 다음, **NorthwindClient.ServiceReference1** 노드를 확장합니다.  
  
5. **Customer** 확인란을 선택한 다음, **마침** 단추를 선택합니다.  
  
   이 단계에서는 서비스의 데이터를 표시할 사용자 인터페이스를 만듭니다.  
  
#### <a name="to-create-the-user-interface"></a>사용자 인터페이스를 만들려면  
  
1. **데이터 원본** 창에서 **Customers** 노드에 대한 바로 가기 메뉴를 열고 **복사**를 선택합니다.  
  
2. **Form1.vb** 또는 **Form1.c** 폼 디자이너에서 바로 가기 메뉴를 열고 **붙여넣기**를 선택합니다.  
  
    <xref:System.Windows.Forms.DataGridView> 컨트롤, <xref:System.Windows.Forms.BindingSource> 구성 요소 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소가 폼에 추가됩니다.  
  
3. **CustomersDataGridView** 컨트롤을 선택한 다음, **속성** 창에서 **Dock** 속성을 **Fill**로 설정합니다.  
  
4. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 합니다 **Form1** 노드 선택 **코드 보기** 코드 편집기를 열고 다음 Imports 또는 Using 문을에서 추가 파일의 위쪽:  
  
   ```vb  
   Imports NorthwindClient.ServiceReference1  
   ```  
  
   ```csharp  
   using NorthwindClient.ServiceReference1;  
   ```  
  
5. 다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.  
  
   ```vb  
   Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
           Dim proxy As New NorthwindEntities _  
   (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))  
           Me.CustomersBindingSource.DataSource = proxy.Customers  
       End Sub  
   ```  
  
   ```csharp  
   private void Form1_Load(object sender, EventArgs e)  
   {  
   NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));  
   this.CustomersBindingSource.DataSource = proxy.Customers;  
   }  
  
   ```  
  
6. **솔루션 탐색기**NorthwindCustomers.svc 파일에 대 한 바로 가기 메뉴를 열고 선택 **브라우저에서 보기**합니다. Internet Explorer가 열리고 서비스에 대한 XML 스키마가 표시됩니다.  
  
7. Internet Explorer 주소 표시줄에서 URL을 복사합니다.  
  
8. 4단계에서 추가한 코드에서 `http://localhost:53161/NorthwindCustomers.svc/`를 선택하여 방금 복사한 URL로 바꿉니다.  
  
9. 메뉴 모음에서 선택 **디버그**를 **디버깅 시작** 응용 프로그램을 실행 합니다. 고객 정보가 표시됩니다.  
  
   이제 NorthwindCustomers 서비스의 고객 목록을 표시하는 애플리케이션이 만들어졌습니다. 이 서비스를 통해 추가 데이터를 노출하려면 Northwind 데이터베이스의 다른 테이블을 포함하도록 [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]을 수정하면 됩니다.  
  
   선택 사항인 다음 단계에서는 서비스에서 반환하는 데이터를 필터링하는 방법에 대해 설명합니다.  
  
## <a name="adding-filtering-capabilities"></a>필터링 기능 추가  
 이 단계에서는 고객의 구/군/시/를 기준으로 데이터를 필터링하도록 애플리케이션을 사용자 지정합니다.  
  
#### <a name="to-add-filtering-by-city"></a>구/군/시 기준 필터링을 추가하려면  
  
1. **솔루션 탐색기**에서 **Form1.vb** 또는 **Form1.cs** 노드의 바로 가기 메뉴를 열고 **열기**를 선택합니다.  
  
2. <xref:System.Windows.Forms.Button>도구 상자**에서 <xref:System.Windows.Forms.TextBox> 컨트롤 및**  컨트롤을 폼에 추가합니다.  
  
3. 바로 가기 메뉴를 열고 합니다 <xref:System.Windows.Forms.Button> 컨트롤을 선택 **코드 보기**에서 다음 코드를 추가 하 고는 `Button1_Click` 이벤트 처리기:  
  
    ```vb  
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
            Dim proxy As New northwindEntities _  
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))  
            Dim city As String = TextBox1.Text  
  
            If city <> "" Then  
                Me.CustomersBindingSource.DataSource = From c In _  
             proxy.Customers Where c.City = city  
            End If  
  
        End Sub  
    ```  
  
    ```csharp  
    private void Button1_Click(object sender, EventArgs e)  
    {  
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));  
    string city = TextBox1.Text;  
  
    if (!string.IsNullOrEmpty(city)) {  
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;  
    }  
  
    }  
    ```  
  
4. 앞의 코드에서 `http://localhost:53161/NorthwindCustomers.svc`를 `Form1_Load` 이벤트 처리기의 URL로 바꿉니다.  
  
5. 메뉴 모음에서 선택 **디버그**를 **디버깅 시작** 응용 프로그램을 실행 합니다.  
  
6. 텍스트 상자에 **London**을 입력한 다음, 단추를 선택합니다. London의 고객만 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)   
 [방법: WCF 데이터 서비스 참조 추가, 업데이트 또는 제거](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)
