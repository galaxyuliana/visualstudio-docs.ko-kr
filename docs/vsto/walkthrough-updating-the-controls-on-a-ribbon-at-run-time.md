---
title: '연습: 런타임에 리본의 컨트롤 업데이트'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- updating Ribbon controls
- Ribbon [Office development in Visual Studio], dynamic menu
- dynamic menus [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], updating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e293a0136e6ae2d8b6a6747201e484fdea43f91e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60067237"
---
# <a name="walkthrough-update-the-controls-on-a-ribbon-at-runtime"></a>연습: 런타임에 리본의 컨트롤 업데이트

이 연습에서는 리본 개체 모델을 사용 하 여 Office 응용 프로그램에 리본 메뉴가 로드 된 후 리본에서 컨트롤을 업데이트 하는 방법에 설명 합니다.

[!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

이 예제에서는 Northwind 샘플 데이터베이스에서 데이터를 끌어와 Microsoft Office Outlook의 콤보 상자 및 메뉴를 채웁니다. 자동으로 이러한 컨트롤에서 선택한 항목의 필드를 같은 채울 **하** 및 **주체** 전자 메일 메시지의 합니다.

이 연습에서는 다음 작업을 수행합니다.

- 새 Outlook VSTO 추가 기능에 프로젝트를 만듭니다.

- 사용자 지정 리본 그룹을 디자인 합니다.

- 기본 제공 탭 사용자 지정 그룹을 추가 합니다.

- 런타임에 리본 메뉴의 컨트롤을 업데이트 합니다.

> [!NOTE]
> 일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- Microsoft Outlook

## <a name="create-a-new-outlook-vsto-add-in-project"></a>새 Outlook VSTO 추가 기능에서 프로젝트 만들기

먼저 Outlook VSTO 추가 기능 프로젝트를 만듭니다.

### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>새 Outlook VSTO 추가 기능 프로젝트를 만들려면

1. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 이름에서 Outlook VSTO 추가 기능 프로젝트를 만듭니다 **Ribbon_Update_At_Runtime**합니다.

2. **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기**를 선택합니다.

3. 기본 프로젝트 디렉터리에 프로젝트를 저장합니다.

     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.

## <a name="design-a-custom-ribbon-group"></a>사용자 지정 리본 그룹 디자인

이 예제에 대 한 리본 메뉴 사용자는 새 메일 메시지를 작성 하는 경우에 표시 됩니다. 리본 사용자 지정 그룹을 만들려면 먼저 프로젝트에 리본 항목을 추가 하 고 리본 디자이너에서 그룹을 디자인 합니다. 이 사용자 지정 그룹 이름은 끌어오는 방법으로 고객에 게 후속 메일 메시지를 생성 하 고 주문 데이터베이스에서 기록 하는 데 도움이 됩니다.

### <a name="to-design-a-custom-group"></a>사용자 지정 그룹을 디자인하려면

1. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

2. **새 항목 추가** 대화 상자에서 **리본(비주얼 디자이너)** 을 선택합니다.

3. 새 리본의 이름을 변경할 **CustomerRibbon**를 클릭 하 고 **추가**합니다.

     합니다 *CustomerRibbon.cs* 하거나 *CustomerRibbon.vb* 파일이 리본 디자이너에서 열리고 기본 탭 및 그룹이 표시 됩니다.

4. 리본 디자이너를 클릭하여 선택합니다.

5. 에 **속성** 창 옆에 있는 드롭다운 화살표를 클릭 합니다 **RibbonType** 속성을 클릭 한 다음 **Microsoft.Outlook.Mail.Compose**합니다.

     이렇게 하면 리본 메뉴가 사용자는 Outlook에서 새 메일 메시지를 작성할 때 나타납니다.

6. 리본 디자이너에서 클릭 **Group1** 하 여 선택 합니다.

7. 에 **속성** 창에서 **레이블** 하 **Customer Purchases**합니다.

8. **Office 리본 컨트롤** 탭의 **도구 상자**, 끌어를 **콤보 상자** 에 **Customer Purchases** 그룹.

9. 클릭 **ComboBox1** 하 여 선택 합니다.

10. 에 **속성** 창에서 **레이블** 에 **고객**합니다.

11. **Office 리본 컨트롤** 탭의 **도구 상자**, 끌어를 **메뉴** 에 **Customer Purchases** 그룹.

12. 에 **속성** 창에서 **레이블** 에 **Product Purchased**합니다.

13. 설정할 **동적** 하 **true**합니다.

     이 통해 추가 하 고 Office 응용 프로그램에 리본 메뉴가 로드 된 후 런타임에 메뉴의 컨트롤을 제거할 수 있습니다.

## <a name="add-the-custom-group-to-a-built-in-tab"></a>기본 제공 탭 사용자 지정 그룹 추가

기본 제공 탭은 Outlook 탐색기 또는 검사기의 리본 메뉴에 이미 있는 탭입니다. 이 절차에서는 기본 제공 탭에 사용자 지정 그룹을 추가하고 탭에서 사용자 지정 그룹의 위치를 지정합니다.

### <a name="to-add-the-custom-group-to-a-built-in-tab"></a>기본 제공 탭에 사용자 지정 그룹을 추가하려면

1. 클릭 합니다 **TabAddins (기본 제공)** 탭을 선택 합니다.

2. 에 **속성** 창 확장 합니다 **ControlId** 속성을 설정 **OfficeId** 에 **tabnewmailmessage로 설정**합니다.

     추가 합니다 **Customer Purchases** 그룹에 **메시지** 새 메일 메시지에 나타나는 리본 메뉴의 탭 합니다.

3. 클릭 합니다 **Customer Purchases** 그룹을 선택 합니다.

4. **속성** 창 확장를 **위치** 속성 옆에 있는 드롭다운 화살표를 클릭 합니다 **PositionType** 속성을 클릭 한 다음  **BeforeOfficeId**합니다.

5. 설정 된 **OfficeId** 속성을 **groupclipboard로 설정**합니다.

     이 배치를 **Customer Purchases** 하기 전에 그룹을 **클립보드** 그룹의 **메시지** 탭.

## <a name="create-the-data-source"></a>데이터 원본 만들기

**데이터 원본** 창을 사용하여 형식화된 데이터 집합을 프로젝트에 추가합니다.

### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면

1. **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.

     이 시작 합니다 **데이터 소스 구성 마법사**합니다.

2. 선택 **데이터베이스**를 클릭 하 고 **다음**합니다.

3. 선택 **데이터 집합**를 클릭 하 고 **다음**합니다.

4. Northwind 샘플 Microsoft SQL Server Compact 4.0 데이터베이스에 데이터 연결을 선택 하거나 새 연결을 사용 하 여 추가 합니다 **새 연결** 단추입니다.

5. 연결을 선택 했거나 만든 후 클릭 **다음**합니다.

6. 클릭 **다음** 연결 문자열을 저장 합니다.

7. 에 **데이터베이스 개체 선택** 페이지에서 **테이블**합니다.

8. 다음 표의 옆에 있는 확인란을 각각 선택합니다.

    1. **고객**

    2. **주문 세부 정보**

    3. **주문**

    4. **제품**

9. **마침**을 클릭합니다.

## <a name="update-controls-in-the-custom-group-at-runtime"></a>런타임 시 사용자 지정 그룹의 컨트롤 업데이트

리본 개체 모델을 사용하여 다음 작업을 수행합니다.

- 고객 이름을 추가 합니다 **고객** 콤보 상자입니다.

- 메뉴 및 단추 컨트롤을 추가 합니다 **Products Purchased** 판매 주문 및 제품을 나타내는 메뉴 판매 합니다.

- To, 제목 및 본문을 채울 데이터를 사용 하 여 새 메일 메시지의 필드를 **고객이** 콤보 상자 및 **Products Purchased** 메뉴.

### <a name="to-update-controls-in-the-custom-group-by-using-the-ribbon-object-model"></a>리본 개체 모델을 사용하여 사용자 지정 그룹의 컨트롤을 업데이트하려면

1. **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.

2. 에 **참조 추가** 대화 상자에서 클릭는 **.NET** 탭을 선택 합니다 **System.Data.Linq** 어셈블리 및 클릭 한 다음 **확인**.

    이 어셈블리에는 LINQ(Language-Integrated Queries)를 사용하기 위한 클래스가 포함되어 있습니다. LINQ를 사용하여 Northwind 데이터베이스의 데이터로 사용자 지정 그룹의 컨트롤을 채웁니다.

3. **솔루션 탐색기**, 클릭 **CustomerRibbon.cs** 하거나 **CustomerRibbon.vb** 하 여 선택 합니다.

4. **보기** 메뉴에서 **코드**를 클릭합니다.

    코드 편집기에서 리본 코드 파일이 열립니다.

5. 리본 코드 파일 맨 위에 다음 문을 추가합니다. 이러한 문을 통해 Outlook PIA(주 interop 어셈블리)의 네임스페이스 및 LINQ 네임스페이스에 쉽게 액세스할 수 있습니다.

    [!code-csharp[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#1)]
    [!code-vb[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#1)]

6. 안에 다음 코드를 추가 합니다 `CustomerRibbon` 클래스입니다. 이 코드는 Northwind 데이터베이스의 Customer, Orders, Order Details 및 Product 테이블 정보를 저장하는 데 사용할 데이터 테이블 및 테이블 어댑터를 선언합니다.

    [!code-csharp[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#2)]
    [!code-vb[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#2)]

7. `CustomerRibbon` 클래스에 다음 코드 블록을 추가합니다. 이 코드는 런타임에 리본 컨트롤을 만드는 세 가지 도우미 메서드를 추가 합니다.

    [!code-csharp[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#3)]
    [!code-vb[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#3)]

8. `CustomerRibbon_Load` 이벤트 처리기 메서드를 다음 코드로 바꿉니다. 이 코드는 LINQ 쿼리를 사용하여 다음 작업을 수행합니다.

   - 채울 합니다 **고객** Northwind 데이터베이스의 20 개 고객의 이름과 ID를 사용 하 여 콤보 상자입니다.

   - `PopulateSalesOrderInfo` 도우미 메서드를 호출합니다. 이 메서드를 업데이트 합니다 **ProductsPurchased** 는 현재 선택한 고객과 관련 된 판매 주문 번호를 사용 하 여 메뉴.

     [!code-csharp[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#4)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#4)]

9. `CustomerRibbon` 클래스에 다음 코드를 추가합니다. 이 코드는 LINQ 쿼리를 사용하여 다음 작업을 수행합니다.

   - 하위 메뉴를 추가 합니다 **ProductsPurchased** 는 선택한 고객과 관련 된 각 판매 주문에 대 한 메뉴입니다.

   - 판매 주문과 관련된 제품에 대한 단추를 각 하위 메뉴에 추가합니다.

   - 각 단추에 이벤트 처리기를 추가합니다.

     [!code-csharp[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#6)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#6)]

10. **솔루션 탐색기**, 리본 코드 파일을 두 번 클릭 합니다.

     리본 디자이너가 열립니다.

11. 리본 디자이너에서 두 번 클릭 합니다 **고객** 콤보 상자입니다.

     리본 코드 파일이 코드 편집기에서 열리고 `ComboBox1_TextChanged` 이벤트 처리기가 나타납니다.

12. `ComboBox1_TextChanged` 이벤트 처리기를 다음 코드로 바꿉니다. 이 코드는 다음 작업을 수행합니다.

    - `PopulateSalesOrderInfo` 도우미 메서드를 호출합니다. 이 메서드를 업데이트 합니다 **Products Purchased** 메뉴는 선택한 고객과 관련 된 판매 주문이 있습니다.

    - `PopulateMailItem` 도우미 메서드를 호출하고 선택한 고객 이름인 현재 텍스트를 전달합니다. 이 메서드를, 제목 및 본문 채웁니다 새 메일 메시지의 필드입니다.

      [!code-csharp[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#5)]
      [!code-vb[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#5)]

13. `Click` 클래스에 다음 `CustomerRibbon` 이벤트 처리기를 추가합니다. 이 코드는 새 메일 메시지의 본문 필드에 선택 된 제품의 이름을 추가합니다.

     [!code-csharp[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#8)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#8)]

14. `CustomerRibbon` 클래스에 다음 코드를 추가합니다. 이 코드는 다음 작업을 수행합니다.

    - 현재 선택한 고객의 전자 메일 주소를 사용 하 여 새 메일 메시지의 받는 사람 줄을 채웁니다.

    - 새 메일 메시지의 제목 및 본문 필드에 텍스트를 추가합니다.

      [!code-csharp[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#7)]
      [!code-vb[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#7)]

## <a name="test-the-controls-in-the-custom-group"></a>사용자 지정 그룹의 컨트롤을 테스트

사용자 지정 그룹에 명명 된 Outlook에서 새 메일 양식을 열면 **Customer Purchases** 에 표시 되는 **메시지** 리본 메뉴의 탭 합니다.

고객 후속 메일 메시지를 만들려면 고객을 선택 하 고 고객이 구매한 제품을 선택 합니다. 컨트롤에는 **Customer Purchases** 그룹 Northwind 데이터베이스에서 데이터를 사용 하 여 런타임에 업데이트 됩니다.

### <a name="to-test-the-controls-in-the-custom-group"></a>사용자 지정 그룹의 컨트롤을 테스트하려면

1. 키를 눌러 **F5** 프로젝트를 실행 합니다.

     Outlook이 시작됩니다.

2. Outlook에서에 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **메일 메시지**합니다.

     다음 작업이 수행됩니다.

    - 새 메일 메시지 검사기 창이 나타납니다.

    - 에 **메시지** 리본 메뉴의 탭을 **Customer Purchases** 그룹 앞에 표시를 **클립보드** 그룹입니다.

    - 합니다 **고객** 그룹에서 콤보 상자가 Northwind 데이터베이스의 고객의 이름이으로 업데이트 됩니다.

3. **메시지** 리본 메뉴의 탭에서를 **Customer Purchases** 그룹에서에서 고객을 선택 합니다 **고객** 콤보 상자.

     다음 작업이 수행됩니다.

    - 합니다 **Products Purchased** 메뉴는 선택한 고객에 대 한 각 판매 주문을 표시 하도록 업데이트 됩니다.

    - 각 판매 주문 하위 메뉴가 해당 주문에서 구매된 제품을 표시하도록 업데이트됩니다.

    - 선택된 된 고객의 전자 메일 주소에 추가 됩니다는 **에** 줄 메일 메시지, 제목 및 메일 메시지의 본문 텍스트가 채워집니다.

4. 클릭 합니다 **Products Purchases** 메뉴에서 판매 주문을 가리킨 및 판매 주문에서 제품을 클릭 합니다.

     제품 이름이 메일 메시지의 본문에 추가됩니다.

## <a name="next-steps"></a>다음 단계

다음 항목에서는 Office UI를 사용자 지정하는 방법에 대해 더 자세히 설명합니다.

- 문서 수준 사용자 지정에 컨텍스트 기반 UI를 추가합니다. 자세한 내용은 [작업창 개요](../vsto/actions-pane-overview.md)합니다.

- 표준 또는 사용자 지정 Microsoft Office Outlook 양식을 확장합니다. 자세한 내용은 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)합니다.

- Outlook에 사용자 지정 작업창을 추가합니다. 자세한 내용은 [사용자 지정 작업창](../vsto/custom-task-panes.md)합니다.

## <a name="see-also"></a>참고자료

- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
- [리본 개요](../vsto/ribbon-overview.md)
- [LINQ(Language-Integrated Query)](/dotnet/csharp/linq/index)
- [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)
- [Outlook의 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)
- [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)
- [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)
- [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [방법: 추가 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)