---
title: ADO.NET을 사용하여 간단한 데이터 애플리케이션 만들기
ms.date: 08/23/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 2222841f-e443-4a3d-8c70-4506aa905193
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 833f4fba621c41a51adca1368c784df313419f97
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54945517"
---
# <a name="create-a-simple-data-application-by-using-adonet"></a>ADO.NET을 사용하여 간단한 데이터 애플리케이션 만들기

데이터베이스의 데이터를 조작하는 애플리케이션을 만들면 연결 문자열 정의, 데이터 삽입 및 저장 프로시저 실행과 같은 기본 작업을 수행합니다. 이 항목에 따라 시각적 개체를 사용 하 여 간단한 Windows Forms "데이터 폼" 응용 프로그램 내에서 데이터베이스와 상호 작용 하는 방법을 검색할 수 있습니다 C# 또는 Visual Basic 및 ADO.NET입니다.  모든.NET 데이터 기술-LINQ to SQL과 Entity Framework 데이터 집합을 포함 하 여, 궁극적으로이 문서에 나와 있는 것과 매우 유사한 단계를 수행 합니다.

이 문서는 데이터베이스에서 데이터를 빠른 방식으로 참여 하는 간단한 방법을 보여 줍니다. 응용 프로그램을 trivial이 아닌 방법으로 데이터를 수정 하 고 데이터베이스를 업데이트 하는 경우에 Entity Framework를 사용 하 여 및 데이터 바인딩 기본 데이터의 변경 내용에 사용자 인터페이스 컨트롤을 자동으로 동기화를 사용 해야 합니다.

> [!IMPORTANT]
> 코드를 간단히 유지하기 위해 프로덕션에 사용하는 예외 처리는 포함되어 있지 않습니다.

## <a name="prerequisites"></a>전제 조건

응용 프로그램을 만들려면 다음이 필요 합니다.

-   Visual Studio.

-   SQL Server Express LocalDB. SQL Server Express LocalDB가 없는 경우에서 설치할 수 있습니다 합니다 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express)합니다.

이 항목에는 Visual Studio IDE의 기본 기능에 익숙한 및, 수 있습니다 Windows Forms 응용 프로그램을 만드는 추가 단추 및 기타 컨트롤을 폼에 배치 합니다. 프로젝트에 폼 컨트롤 및 간단한 이벤트 코드의 속성을 설정 가정 합니다. 이러한 작업에 익숙하지 경우 완료 하는 것이 좋습니다 합니다 [시각적 개체를 사용 하 여 시작 C# 및 Visual Basic](../ide/quickstart-visual-basic-console.md) 이 연습을 시작 하기 전에 항목입니다.

## <a name="set-up-the-sample-database"></a>샘플 데이터베이스 설정

다음 단계를 수행 하 여 샘플 데이터베이스를 만듭니다.

1. Visual Studio에서 엽니다는 **서버 탐색기** 창입니다.

2. 마우스 오른쪽 단추로 클릭 **데이터 연결** 선택한 **새 SQL Server 데이터베이스 만들기**합니다.

3. 에 **서버 이름** 텍스트 상자에 입력 합니다 **(localdb) \mssqllocaldb**합니다.

4. 에 **새 데이터베이스 이름** 텍스트 상자에 입력 합니다 **Sales**를 선택한 **확인**합니다.

     빈 **Sales** 데이터베이스가 작성 되 고 서버 탐색기에서 데이터 연결 노드에 추가 합니다.

5. 마우스 오른쪽 단추로 클릭 합니다 **Sales** 데이터 연결 및 선택 **새 쿼리**합니다.

     쿼리 편집기 창이 열립니다.

6. 복사 합니다 [Sales Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/data-tools/samples/sales.sql) 클립보드에 합니다.

7. T-SQL 스크립트, 쿼리 편집기에 붙여넣고 선택한 합니다 **Execute** 단추입니다.

     짧은 시간 후 쿼리 실행이 완료 하 고 데이터베이스 개체 생성 됩니다. 데이터베이스에는 두 개의 테이블이 있습니다. 고객과 주문입니다. 이러한 테이블에 데이터가 없는 처음에 있지만 앞으로 만들 응용 프로그램을 실행 하는 경우 데이터를 추가할 수 있습니다. 또한 데이터베이스 4 개의 간단한 저장된 프로시저를 포함합니다.

## <a name="create-the-forms-and-add-controls"></a>폼 만들기 및 컨트롤 추가

1. Windows Forms 애플리케이션의 프로젝트를 만든 다음, 이름을 **SimpleDataApp**으로 지정합니다.

    Visual Studio에서는 프로젝트와 **Form1**이라는 빈 Windows 양식을 포함한 여러 파일을 만듭니다.

2. 프로젝트에 두 개의 Windows 양식을 추가하여 총 세 개의 양식을 만든 다음, 다음 이름을 지정합니다.

   -   **탐색**

   -   **NewCustomer**

   -   **FillOrCancel**

3. 각 폼에 대해 다음 그림에 나오는 텍스트 상자, 단추 및 기타 컨트롤을 추가합니다. 각 컨트롤에 대해 테이블이 설명하는 속성을 설정합니다.

   > [!NOTE]
   > 그룹 상자 및 레이블 컨트롤도 선명성을 더해 주지만 코드에서는 사용하지 않습니다.

   **탐색 양식**

   ![검색 대화 상자](../data-tools/media/simpleappnav.png)

|Navigation 폼 컨트롤|속성|
| - |----------------|
|단추|Name = btnGoToAdd|
|단추|Name = btnGoToFillOrCancel|
|단추|Name = btnExit|

 **NewCustomer 양식**

 ![새 고객을 추가하고 주문하기](../data-tools/media/simpleappnewcust.png)

|NewCustomer 폼 컨트롤|속성|
| - |----------------|
|TextBox|Name = txtCustomerName|
|TextBox|Name = txtCustomerID<br /><br /> Readonly = True|
|단추|Name = btnCreateAccount|
|NumericUpdown|DecimalPlaces = 0<br /><br /> Maximum = 5000<br /><br /> Name = numOrderAmount|
|DateTimePicker|Format = Short<br /><br /> Name = dtpOrderDate|
|단추|Name = btnPlaceOrder|
|단추|Name = btnAddAnotherAccount|
|단추|Name = btnAddFinish|

 **FillOrCancel 양식**

 ![주문 입력 또는 취소](../data-tools/media/simpleappcancelfill.png)

|FillOrCancel 폼 컨트롤|속성|
| - |----------------|
|TextBox|Name = txtOrderID|
|단추|Name = btnFindByOrderID|
|DateTimePicker|Format = Short<br /><br /> Name = dtpFillDate|
|DataGridView|Name = dgvCustomerOrders<br /><br /> Readonly = True<br /><br /> RowHeadersVisible = False|
|단추|Name = btnCancelOrder|
|단추|Name = btnFillOrder|
|단추|Name = btnFinishUpdates|

## <a name="store-the-connection-string"></a>연결 문자열 저장
 응용 프로그램이 데이터베이스에 대한 연결을 열려면 응용 프로그램에는 연결 문자열에 액세스할 수 있어야 합니다. 각 폼에 문자열을 수동으로 입력를 방지 하려면 문자열을 저장 합니다 *App.config* 프로젝트에서 파일을 응용 프로그램의 폼에서 메서드를 호출할 때 문자열을 반환 하는 메서드를 만듭니다.

 마우스 오른쪽 단추로 클릭 하 여 연결 문자열을 찾을 수 있습니다 합니다 **Sales** 에서 데이터 연결 **서버 탐색기** 선택 하 고 **속성**합니다. 찾을 합니다 **ConnectionString** 속성을 사용 하 여 **Ctrl**+**A**, **Ctrl**+**C**  선택 하 고 문자열을 클립보드에 복사 합니다.

1.  사용 중인 경우 C#의 **솔루션 탐색기**를 확장 합니다 **속성** 노드 프로젝트를 연 다음를 **생성 되는 Settings.settings** 파일.
    Visual Basic을 사용 하는 경우 **솔루션 탐색기**, 클릭 **모든 파일 표시**를 확장 합니다 **My Project** 노드를 연 다음는 **를Settings.settings** 파일입니다.

2.  에 **이름을** 열, 입력 `connString`합니다.

3.  에 **형식** 목록에서 **(문자열)** 합니다.

4.  에 **범위** 목록에서 **응용 프로그램**합니다.

5.  에 **값** 열 (하지 않고 따옴표 외부), 연결 문자열을 입력 하 고 다음 변경 내용을 저장 합니다.

> [!NOTE]
> 실제 응용 프로그램에서 연결 문자열을 안전 하 게에 설명 된 대로 저장 해야 [연결 문자열 및 구성 파일](/dotnet/framework/data/adonet/connection-strings-and-configuration-files)합니다.

##  <a name="write-the-code-for-the-forms"></a>폼에 대한 코드 작성

이 섹션에서는 각 폼에서 수행 하는 작업의 간략 한 개요를 포함 합니다. 또한 폼에 단추를 클릭할 때 기본 논리를 정의 하는 코드를 제공 합니다.

### <a name="navigation-form"></a>Navigation 폼

응용 프로그램을 실행하면 Navigation 폼이 열립니다. **계정 추가** 단추는 NewCustomer 양식을 엽니다. **주문 이행 또는 취소** 단추를 누르면 FillOrCancel 양식이 열립니다. **끝내기** 단추를 클릭하면 애플리케이션이 닫힙니다.

#### <a name="make-the-navigation-form-the-startup-form"></a>Navigation 폼을 시작 폼으로 만들기

C#을 사용하는 경우 **솔루션 탐색기**에서 **Program.cs**를 연 다음, `Application.Run` 줄을 `Application.Run(new Navigation());`으로 변경합니다.

Visual Basic을 사용 하는 경우 **솔루션 탐색기**오픈 합니다 **속성** 창에서를 **응용 프로그램** 탭을 선택한 후  **SimpleDataApp.Navigation** 에 **시작 폼** 목록입니다.

#### <a name="create-auto-generated-event-handlers"></a>자동으로 생성 된 이벤트 처리기 만들기

빈 이벤트 처리기 메서드를 만드는 탐색 폼에 단추 세 개를 두 번 클릭 합니다. 단추 클릭 이벤트를 발생 시킬 수 있도록 하는 디자이너 코드 파일에서 자동으로 생성 된 코드도 추가 단추를 두 번 클릭 합니다.

#### <a name="add-code-for-the-navigation-form-logic"></a>탐색 폼 논리에 대 한 코드를 추가 합니다.

Navigation 폼에 대 한 코드 페이지에서 전체 세 단추에 대 한 메서드 본문 클릭 이벤트 처리기 다음 코드 에서처럼 합니다.

[!code-csharp[Navigation#1](../data-tools/codesnippet/CSharp/SimpleDataApp/Navigation.cs#1)]
[!code-vb[Navigation#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/Navigation.vb#1)]

### <a name="newcustomer-form"></a>NewCustomer 폼

고객 이름을 입력 하 고 다음을 선택 합니다 **계정 만들기** 단추를 NewCustomer 폼은 고객 계정을 만들고 SQL Server 새 고객 ID는 ID 값을 반환 합니다. 금액과 주문 날짜를 지정 하 고 선택 하 여 새 계정에 대 한 주문을 둘 수는 **주문** 단추입니다.

#### <a name="create-auto-generated-event-handlers"></a>자동으로 생성 된 이벤트 처리기 만들기

빈 Click 만들 각 네 개의 단추를 두 번 클릭 하면 NewCustomer 폼의 각 단추에 대 한 이벤트 처리기입니다. 단추 클릭 이벤트를 발생 시킬 수 있도록 하는 디자이너 코드 파일에서 자동으로 생성 된 코드도 추가 단추를 두 번 클릭 합니다.

#### <a name="add-code-for-the-newcustomer-form-logic"></a>NewCustomer 폼 논리에 대 한 코드를 추가 합니다.

NewCustomer 폼 논리를 완료 하려면 다음이 단계를 수행 합니다.

1. 가져오기는 `System.Data.SqlClient` 네임 스페이스 범위에 완전히 필요가 없습니다 있도록 한정 해당 멤버의 이름입니다.

     ```csharp
     using System.Data.SqlClient;
     ```
     ```vb
     Imports System.Data.SqlClient
     ```

2. 다음 코드 에서처럼 클래스에 몇 가지 변수 및 도우미 메서드를 추가 합니다.

     [!code-csharp[NewCustomer#1](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#1)]
     [!code-vb[NewCustomer#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#1)]

3. 완료 메서드 본문에서 4 개의 단추에 대 한 click 이벤트 처리기 다음 코드에 표시 된 대로 합니다.

     [!code-csharp[NewCustomer#2](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#2)]
     [!code-vb[NewCustomer#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#2)]

### <a name="fillorcancel-form"></a>FillOrCancel 폼

FillOrCancel 폼 주문 ID를 입력 하 고 클릭 하면 주문을 반환 하는 쿼리를 실행 합니다 **주문 찾기** 단추입니다. 반환되는 행은 읽기 전용 데이터 표에 표시됩니다. 선택할 경우 주문을 취소 (X)으로 표시할 수 있습니다는 **주문 취소** 하거나 단추를 표시할 수 있습니다 순서 채워진된 (F)을 선택 합니다 **주문** 단추입니다. 선택 하는 경우는 **주문 찾기** 단추를 다시 업데이트 된 행은 표시 됩니다.

#### <a name="create-auto-generated-event-handlers"></a>자동으로 생성 된 이벤트 처리기 만들기

빈 항목 만들기 단추를 두 번 클릭 하 여 FillOrCancel 폼에 단추 4 개에 대 한 이벤트 처리기를 클릭 합니다. 단추 클릭 이벤트를 발생 시킬 수 있도록 하는 디자이너 코드 파일에서 자동으로 생성 된 코드도 추가 단추를 두 번 클릭 합니다.

#### <a name="add-code-for-the-fillorcancel-form-logic"></a>FillOrCancel 폼 논리에 대 한 코드를 추가 합니다.

FillOrCancel 폼 논리를 완료 하려면 다음이 단계를 수행 합니다.

1. 해당 멤버의 이름을 정규화 할 필요가 없도록 범위로 다음 두 네임 스페이스를 가져옵니다.

     ```csharp
     using System.Data.SqlClient;
     using System.Text.RegularExpressions;
     ```
     ```vb
     Imports System.Data.SqlClient
     Imports System.Text.RegularExpressions
     ```

2. 다음 코드 에서처럼 클래스에는 변수 및 도우미 메서드를 추가 합니다.

     [!code-csharp[FillOrCancel#1](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#1)]
     [!code-vb[FillOrCancel#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#1)]

3. 완료 메서드 본문에서 4 개의 단추에 대 한 click 이벤트 처리기 다음 코드에 표시 된 대로 합니다.

     [!code-csharp[FillOrCancel#2](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#2)]
     [!code-vb[FillOrCancel#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#2)]

## <a name="test-your-application"></a>응용 프로그램 테스트

각 Click 이벤트 처리기를 코딩하고 코딩을 마친 후에 **F5** 키를 선택하여 애플리케이션을 빌드하고 테스트합니다.

## <a name="see-also"></a>참고 항목

- [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)
