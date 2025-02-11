---
title: 폼 간에 데이터 전달 | Microsoft Docs
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
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f6cee865542256906ac1685b937da0e63327a97d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694849"
---
# <a name="pass-data-between-forms"></a>폼 간에 데이터 전달
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 폼 간에 데이터를 전달하기 위한 단계별 지침을 제공합니다. customers 및 orders 테이블에서 Northwind 사용 하 여 고객을 선택 하면 폼 및 두 번째 폼을 선택한 고객의 주문이 표시 됩니다. 이 연습에는 첫 번째 형태에서 데이터를 수신 하는 두 번째 형태에서 메서드를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
> 이 연습에서는 폼 간에 데이터를 전달하는 방식 중 하나만을 보여줍니다. 만드는 데이터를 받는 두 번째 생성자를 포함 하 여 폼에 데이터를 전달 하기 위한 다른 옵션은 하거나는 공용 속성을 만들 설정 데이터를 사용 하 여 첫 번째 형태에서.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- 새로 만들 **Windows 응용 프로그램** 프로젝트입니다.  
  
- 만들기 및 사용 하 여 데이터 집합을 구성 합니다 [데이터 소스 구성 마법사](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다.  
  
- **데이터 원본** 창에서 항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택합니다. 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
- **데이터 원본** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
- 데이터를 표시하는 표가 포함된 두 번째 폼을 만듭니다.  
  
- 특정 고객의 주문을 가져오는 TableAdapter 쿼리를 만듭니다.  
  
- 폼 간에 데이터를 전달합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
- Northwind 샘플 데이터베이스에 대한 액세스.
  
## <a name="create-the-windows-application"></a>Windows 응용 프로그램 만들기  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1. **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2. 프로젝트 이름을 `PassingDataBetweenForms`로 지정합니다.  
  
3. 선택 **Windows Forms 응용 프로그램**, 클릭 **확인**합니다. 자세한 내용은 [클라이언트 응용 프로그램](https://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
     **PassingDataBetweenForms** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## <a name="create-the-data-source"></a>데이터 원본 만들기  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1. **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2. **데이터 원본** 창에서 **새 데이터 원본 추가**를 선택하여 **데이터 원본 구성** 마법사를 시작합니다.  
  
3. **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.  
  
4. **데이터베이스 모델 선택** 페이지에서 **데이터 세트**가 지정되어 있는지 확인한 후, **다음**을 클릭합니다.  
  
5. **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    - Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
    - **새 연결**을 선택하여 **연결 추가/수정** 대화 상자를 시작합니다.  
  
6. 데이터베이스에 암호가 필요하며 중요한 데이터를 포함하도록 옵션이 설정되어 있으면 해당 옵션을 선택한 후, **다음**을 클릭합니다.  
  
7. 에 **응용 프로그램 구성 파일에 연결 문자열을 저장** 페이지에서 클릭 **다음**합니다.  
  
8. **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
9. **Customers** 및 **Orders** 테이블을 선택한 다음, **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 **Customers** 및 **Orders** 테이블이 **데이터 원본** 창에 나타납니다.  
  
## <a name="create-the-first-form-form1"></a>첫 번째 형태 (Form1) 만들기  
 **데이터 원본** 창에서 폼으로 **Customers** 노드를 끌어 데이터 바인딩된 표(<xref:System.Windows.Forms.DataGridView>)를 만들 수 있습니다.  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>폼에서 데이터 바인딩된 표를 만들려면  
  
- 주 **Customers** 노드를 **데이터 원본** 창에서 **Form1**으로 끌어서 놓습니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 모음(<xref:System.Windows.Forms.BindingNavigator>)이 **Form1**에 나타납니다. [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
## <a name="create-the-second-form-form2"></a>두 번째 형태 (Form2) 만들기  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>데이터를 전달할 두 번째 폼을 만들려면  
  
1. **프로젝트** 메뉴에서 **Windows Form 추가**를 선택합니다.  
  
2. 기본 이름인 **Form2**를 그대로 두고 **추가**를 클릭합니다.  
  
3. 주 **Orders** 노드를 **데이터 원본** 창에서 **Form2**로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 모음(<xref:System.Windows.Forms.BindingNavigator>)이 **Form2**에 나타납니다. [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
4. 구성 요소 트레이에서 **OrdersBindingNavigator**를 삭제합니다.  
  
     **OrdersBindingNavigator**가 **Form2**에서 사라집니다.  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>Form1에서 선택한 고객의 주문을 로드 하도록 Form2에 TableAdapter 쿼리 추가  
  
#### <a name="to-create-a-tableadapter-query"></a>TableAdapter 쿼리를 만들려면  
  
1. **솔루션 탐색기**에서 **NorthwindDataSet.xsd** 파일을 두 번 클릭합니다.  
  
2. **OrdersTableAdapter**를 마우스 오른쪽 단추로 클릭하고 **쿼리 추가**를 선택합니다.  
  
3. 기본 옵션인 **SQL 문 사용**을 그대로 둔 후, **다음**을 클릭합니다.  
  
4. 기본 옵션인 **행을 반환하는 SELECT**를 그대로 둔 후, **다음**을 클릭합니다.  
  
5. 쿼리에 WHERE 절을 추가하여 `CustomerID`에 따라 `Orders`를 반환합니다. 이 쿼리는 다음과 같아야 합니다.  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    > 데이터베이스에 대한 올바른 매개 변수 구문을 확인합니다. 예를 들어 Microsoft Access에서 WHERE 절은 다음과 같습니다. `WHERE CustomerID = ?`.  
  
6. **다음**을 클릭합니다.  
  
7. 에 대 한 합니다 **DataTableMethod 이름 입력**, 형식 `FillByCustomerID`합니다.  
  
8. **DataTable 반환** 옵션 선택을 취소한 후, **다음**을 클릭합니다.  
  
9. **마침**을 클릭합니다.  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>Form2에 데이터를 전달할 메서드 만들기  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>데이터를 전달할 메서드를 만들려면  
  
1. **Form2**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택하여 **코드 편집기**에서 **Form2**를 엽니다.  
  
2. 다음 코드를 **Form2**의 `Form2_Load` 메서드 뒤에 추가합니다.  
  
     [!code-csharp[VbRaddataDisplaying#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form2.cs#1)]
     [!code-vb[VbRaddataDisplaying#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form2.vb#1)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>데이터를 전달 하 고 Form2를 표시 하는 Form1에서 메서드를 만듭니다.  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Form2로 데이터를 전달할 메서드를 만들려면  
  
1. **Form1**에서 Customer 데이터 표를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 클릭합니다.  
  
2. **속성** 창에서 **이벤트**를 클릭합니다.  
  
3. **CellDoubleClick** 이벤트를 두 번 클릭합니다.  
  
     코드 편집기가 나타납니다.  
  
4. 다음 샘플과 일치하도록 메서드 정의를 업데이트합니다.  
  
     [!code-csharp[VbRaddataDisplaying#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form1.cs#2)]
     [!code-vb[VbRaddataDisplaying#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form1.vb#2)]  
  
## <a name="run-the-application"></a>애플리케이션 실행  
  
#### <a name="to-run-the-application"></a>애플리케이션을 실행하려면  
  
- F5 키를 눌러 애플리케이션을 실행합니다.  
  
- **Form1**에서 고객 레코드를 두 번 클릭하여 해당 고객의 주문이 포함된 **Form2**를 엽니다.  
  
## <a name="next-steps"></a>다음 단계  
 애플리케이션 요구 사항에 따라 폼 간에 데이터를 전달한 후 몇 단계를 더 수행해야 할 수도 있습니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
- 데이터 세트을 편집하여 데이터베이스 개체를 추가하거나 편집합니다. 자세한 내용은 [데이터 세트 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)을 참조하세요.  
  
- 데이터를 데이터베이스로 다시 보내는 기능을 추가합니다. 자세한 내용은 [데이터를 데이터베이스에 다시 저장](../data-tools/save-data-back-to-the-database.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
