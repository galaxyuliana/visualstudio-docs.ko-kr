---
title: 데이터 세트의 데이터 유효성 검사
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataTable.ColumnChanging
- System.Data.DataTable.ColumnChanging
- System.Data.DataTable.RowChanging
- DataTable.RowChanging
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data validation, datasets
- data validation
- validating data, datasets
- updating datasets, validating data
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 5a8d533b647861b8185a65c926f1783744cded74
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55004398"
---
# <a name="validate-data-in-datasets"></a>데이터 세트의 데이터 유효성 검사
데이터 유효성 검사는 데이터 집합의 스키마 내에서 제약 조건에 따르는 데이터 개체에 입력할 값 확인 프로세스. 유효성 검사 프로세스는 또한 이러한 값은 다음과 같습니다 응용 프로그램에 대해 설정 된 규칙을 확인 합니다. 기본 데이터베이스에 업데이트를 보내기 전에 데이터의 유효성을 검사 하는 것이 좋습니다. 이렇게 하면 오류 뿐 아니라 잠재적인 응용 프로그램와 데이터베이스 간의 왕복 수가 줄어듭니다.

자체 데이터 집합에 유효성 검사를 구축 하 여 데이터 집합에 기록 되는 데이터가 유효한 지 확인할 수 있습니다. 데이터 집합 업데이트 수행 방법에 관계 없이 데이터를 확인할 수 있습니다-구성 요소 내에서 양식 또는 다른 방법으로 컨트롤에서 직접 여부. 데이터 집합 (달리 데이터베이스 백 엔드) 응용 프로그램의 일부 이기 때문에 빌드 응용 프로그램별 유효성 검사 논리 마련 된 공간입니다.

데이터 집합의 partial 클래스 파일에는 응용 프로그램에 유효성 검사를 추가 하는 것이 좋습니다. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]오픈 합니다 **데이터 집합 디자이너** 유효성 검사를 만들려는 열 또는 테이블을 두 번 클릭 합니다. 이 작업을 자동으로 만듭니다는 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기입니다.

## <a name="validate-data"></a>데이터 유효성 검사
 데이터 집합 내에서 유효성 검사는 다음과 같은 방법으로 수행 됩니다.

-   변경 하는 동안 개별 데이터 열에 값을 확인할 수 있는 사용자 고유의 응용 프로그램별 유효성 검사를 만듭니다. 자세한 내용은 [방법: 열 변경 중 데이터 유효성 검사](validate-data-in-datasets.md)합니다.

-   데이터 값은 전체 데이터를 확인할 수 있는 응용 프로그램별 유효성 검사를 직접 만들어 행 변경 됩니다. 자세한 내용은 [방법: 행 변경 중 데이터 유효성 검사](validate-data-in-datasets.md)합니다.

-   데이터 집합의 실제 스키마 정의의 일부로 등 unique 제약 조건 키를 만듭니다.

-   속성을 설정 하 여는 <xref:System.Data.DataColumn> 개체를 같은 <xref:System.Data.DataColumn.MaxLength%2A>, <xref:System.Data.DataColumn.AllowDBNull%2A>, 및 <xref:System.Data.DataColumn.Unique%2A>합니다.

여러 이벤트가 발생 된 <xref:System.Data.DataTable> 변경 레코드에서 발생 하는 경우 개체:

-   합니다 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.ColumnChanged> 도중 및 이후에 개별 열을 변경할 때마다 이벤트가 발생 합니다. <xref:System.Data.DataTable.ColumnChanging> 이벤트는 특정 열에서 변경의 유효성을 검사 하려는 경우에 유용 합니다. 제안된 된 변경에 대 한 정보는 이벤트를 사용 하 여 인수로 전달 됩니다.
-   합니다 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트가 도중 및 이후에 모든 행에서 변경 합니다. <xref:System.Data.DataTable.RowChanging> 이벤트는 보다 일반적인 합니다. 변경 행에서 어딘가에 수행 되는 열 변경에 알 수 없는 나타냅니다.

기본적으로 각 열에 4 개의 이벤트가 발생 합니다. 첫 번째는 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.ColumnChanged> 변경 되는 열에 대해서는 이벤트입니다. 다음은 <xref:System.Data.DataTable.RowChanging> 고 <xref:System.Data.DataTable.RowChanged> 이벤트입니다. 행에 여러 변경 사항이 되 고, 각 변경에 대 한 이벤트를 발생 합니다.

> [!NOTE]
>  데이터 행의 <xref:System.Data.DataRow.BeginEdit%2A> 메서드를 해제 합니다 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 각 개별 열 변경 이벤트. 이 경우 이벤트까지 발생 하지 않습니다는 <xref:System.Data.DataRow.EndEdit%2A> 메서드는 호출 될 때 합니다 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트는 한 번만 발생 합니다. 자세한 내용은 [데이터 집합을 채우는 동안 제약 조건 해제](../data-tools/turn-off-constraints-while-filling-a-dataset.md)합니다.

선택한 이벤트 유효성 검사 수를 원하는 세분성에 따라 달라 집니다. 열이 변경 될 때 즉시 오류를 catch 하는 중요 한 경우 유효성 검사를 사용 하 여 빌드를 <xref:System.Data.DataTable.ColumnChanging> 이벤트입니다. 그렇지 않은 경우 사용 된 <xref:System.Data.DataTable.RowChanging> 이벤트를 한 번에 여러 오류를 catch 될 수 있습니다. 또한 데이터는 구성 되어 있으므로 한 열의 값은 다른 열의 내용에 따라 유효성을 검사를 수행할 동안 유효성 검사는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다.

레코드가 업데이트 되는 <xref:System.Data.DataTable> 개체 변경 내용이 발생으로 변경한 후에 응답할 수 있는 이벤트를 발생 시킵니다.

형식화 된 데이터 집합을 사용 하 여 응용 프로그램에는 강력한 형식의 이벤트 처리기를 만들 수 있습니다. 4 개의 형식화 된 이벤트 처리기를 만들 수 있는 추가: `dataTableNameRowChanging`, `dataTableNameRowChanged`를 `dataTableNameRowDeleting`, 및 `dataTableNameRowDeleted`합니다. 이러한 형식의 이벤트 처리기 코드를 더 쉽게 읽고 쓰는 데는 테이블의 열 이름을 포함 하는 인수를 전달 합니다.

## <a name="data-update-events"></a>데이터 업데이트 이벤트

|이벤트|설명|
|-----------|-----------------|
|<xref:System.Data.DataTable.ColumnChanging>|열에 값이 변경 됩니다. 이벤트 제안 된 새 값과 함께, 행 및 열을 전달합니다.|
|<xref:System.Data.DataTable.ColumnChanged>|열에 값을 변경 되었습니다. 이벤트 제안 된 값과 함께, 행 및 열을 전달합니다.|
|<xref:System.Data.DataTable.RowChanging>|에 대 한 변경 내용을 <xref:System.Data.DataRow> 개체를 데이터 집합에 다시 커밋할 수 있습니다. 호출 하지 않은 경우는 <xref:System.Data.DataRow.BeginEdit%2A> 메서드를 <xref:System.Data.DataTable.RowChanging> 열에 각 변경에 대 한 이벤트가 발생 직후는 <xref:System.Data.DataTable.ColumnChanging> 이벤트가 발생 합니다. 호출 하면 <xref:System.Data.DataRow.BeginEdit%2A> 옵션을 변경 하기 전에 <xref:System.Data.DataTable.RowChanging> 호출 하는 경우에 이벤트가 발생 된 <xref:System.Data.DataRow.EndEdit%2A> 메서드.<br /><br /> 이벤트가 수행 중인 작업 (변경, 삽입 및 등)의 유형을 나타내는 값을 행을 전달 합니다.|
|<xref:System.Data.DataTable.RowChanged>|행이 변경 되었습니다. 이벤트가 수행 중인 작업 (변경, 삽입 및 등)의 유형을 나타내는 값을 행을 전달 합니다.|
|<xref:System.Data.DataTable.RowDeleting>|행을 삭제 하는 중입니다. 이벤트 (삭제) 작업의 유형이 수행될지를 나타내는 값을 행을 전달 합니다.|
|<xref:System.Data.DataTable.RowDeleted>|행 삭제 되었습니다. 이벤트 (삭제) 작업의 유형이 수행될지를 나타내는 값을 행을 전달 합니다.|

합니다 <xref:System.Data.DataTable.ColumnChanging>, <xref:System.Data.DataTable.RowChanging>, 및 <xref:System.Data.DataTable.RowDeleting> 업데이트 프로세스 중 이벤트가 발생 합니다. 데이터 유효성 검사 또는 다른 유형의 처리를 수행 합니다. 이러한 이벤트를 사용할 수 있습니다. 이기 때문에 업데이트 프로세스에서 이러한 이벤트 중에서 업데이트를 방지 하는 예외를 throw 하 여 취소할 수 있습니다 완료 합니다.

합니다 <xref:System.Data.DataTable.ColumnChanged>, <xref:System.Data.DataTable.RowChanged> 및 <xref:System.Data.DataTable.RowDeleted> 업데이트가 성공적으로 완료 된 때 발생 하는 알림 이벤트입니다. 이러한 이벤트는 다른 업데이트에 성공에 따라 조치를 취할 하려고 할 때 유용 합니다.

## <a name="validate-data-during-column-changes"></a>열 변경 중 데이터 유효성 검사

> [!NOTE]
>  합니다 **데이터 집합 디자이너** 는 유효성 검사 논리 데이터 집합에 추가할 수 있습니다 partial 클래스를 만듭니다. 디자이너에서 생성 된 데이터 집합을 삭제 하거나 partial 클래스에서 코드를 변경 하지 않습니다.

데이터 열의 값이 변경에 응답 하 여 데이터를 확인할 수 있습니다는 <xref:System.Data.DataTable.ColumnChanging> 이벤트입니다. 이 이벤트는 이벤트 인수를 전달 발생 하면 (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>) 현재 열에 대해 제안 되는 값이 들어 있는입니다. 내용에 따라 `e.ProposedValue`를 할 수 있습니다.

-   아무 것도 수행 하 여 제안 된 값을 수락 합니다.

-   열이 오류를 설정 하 여 제안 된 값을 거부 (<xref:System.Data.DataRow.SetColumnError%2A>)에서 열 변경 이벤트 처리기 내에서.

-   필요에 따라 사용 하 여는 <xref:System.Windows.Forms.ErrorProvider> 컨트롤을 사용자에 게 오류 메시지를 표시 합니다. 자세한 내용은 [ErrorProvider 구성 요소](/dotnet/framework/winforms/controls/errorprovider-component-windows-forms)를 참조하세요.

하는 동안 유효성 검사를 수행할 수도 있습니다는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다.

## <a name="validate-data-during-row-changes"></a>행 변경 중 데이터 유효성 검사
응용 프로그램의 요구 사항을 충족 하는 데이터의 유효성을 검사 하려는 각 열에 포함 되어 있는지 확인 하는 코드를 작성할 수 있습니다. 제안 된 값을 수용할 수 없으면 오류가 있음을 나타내도록 열을 설정 하 여이 작업을 수행 합니다. 다음 예제에서는 설정 열 오류 때는 `Quantity` 열이 0 보다 작거나. 행 변경 이벤트 처리기에는 다음 예제에서는 유사 합니다.

### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>유효성을 검사할 때 행 데이터 변경 (Visual Basic)

1.  **데이터 세트 디자이너**에서 데이터 세트를 엽니다. 자세한 내용은 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.

2.  유효성을 검사 하려는 테이블의 제목 표시줄 두 번 클릭 합니다. 이 작업을 자동으로 만듭니다는 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기는 <xref:System.Data.DataTable> 데이터 집합의 partial 클래스 파일에서 합니다.

    > [!TIP]
    >  행 변경 이벤트 처리기를 만들려는 테이블 이름 왼쪽에 두 번 클릭 합니다. 테이블 이름을 두 번 클릭 하면 편집할 수 있습니다.

     [!code-vb[VbRaddataValidating#3](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_1.vb)]

### <a name="to-validate-data-when-a-row-changes-c"></a>데이터 행이 변경 될 때 유효성을 검사 하려면 (C#)

1.  **데이터 세트 디자이너**에서 데이터 세트를 엽니다. 자세한 내용은 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.

2.  유효성을 검사 하려는 테이블의 제목 표시줄 두 번 클릭 합니다. 이 작업에 대 한 partial 클래스 파일을 만듭니다는 <xref:System.Data.DataTable>합니다.

    > [!NOTE]
    >  합니다 **데이터 집합 디자이너** 에 대 한 이벤트 처리기를 자동으로 만들어지지 않습니다는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다. 처리 하는 메서드를 만들어야 합니다 <xref:System.Data.DataTable.RowChanging> 테이블의 초기화 메서드에서 이벤트를 후크 이벤트 및 코드를 실행된 합니다.

3.  Partial 클래스에 다음 코드를 복사 합니다.

    ```csharp
    public override void EndInit()
    {
        base.EndInit();
        Order_DetailsRowChanging += TestRowChangeEvent;
    }

    public void TestRowChangeEvent(object sender, Order_DetailsRowChangeEvent e)
    {
        if ((short)e.Row.Quantity <= 0)
        {
            e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
        }
        else
        {
            e.Row.SetColumnError("Quantity", "");
        }
    }
    ```

## <a name="to-retrieve-changed-rows"></a>변경 된 행을 검색 하려면
데이터 테이블의 각 행에는 <xref:System.Data.DataRow.RowState%2A> 속성의 값을 사용 하 여 해당 행의 현재 상태는 추적 하는 <xref:System.Data.DataRowState> 열거형입니다. 호출 하 여 데이터 집합 또는 데이터 테이블에서 변경 된 행을 반환할 수 있습니다 합니다 `GetChanges` 메서드를 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>합니다. 호출 하기 전에 변경 내용이 있는지 확인할 수 있습니다 `GetChanges` 를 호출 하 여는 <xref:System.Data.DataSet.HasChanges%2A> 메서드의 데이터 집합입니다.

> [!NOTE]
>  데이터 집합 또는 데이터 테이블에 변경 내용을 커밋한 후 (호출 하 여 합니다 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드), `GetChanges` 메서드 데이터를 반환 하지. 응용 프로그램을 변경 된 행을 처리 하는 경우 호출 하기 전에 변경 내용을 처리 해야 합니다는 `AcceptChanges` 메서드.

호출 된 <xref:System.Data.DataSet.GetChanges%2A> 메서드는 데이터 집합 또는 데이터 테이블의 변경 된 레코드만 포함 된 새 데이터 집합 또는 데이터 테이블을 반환 합니다. 특정 레코드를 가져오려는 경우-예를 들어, 새 레코드만 또는 수정 된 레코드만-에서 값을 전달할 수 있습니다 합니다 <xref:System.Data.DataRowState> 열거형에 대 한 매개 변수로 `GetChanges` 메서드.

사용 된 <xref:System.Data.DataRowVersion> 행 (예를 들어 원래 있던 값 처리 하기 전에 행)의 다른 버전에 액세스 하는 열거형입니다.

### <a name="to-get-all-changed-records-from-a-dataset"></a>데이터 집합에서 변경 된 모든 레코드를 가져오려면

-   호출 된 <xref:System.Data.DataSet.GetChanges%2A> 데이터 집합의 메서드.

     다음 예제에서는 라는 새 데이터 집합을 만듭니다 `changedRecords` 라는 다른 데이터 집합에서 변경된 된 모든 레코드를 사용 하 여 채웁니다 `dataSet1`합니다.

     [!code-csharp[VbRaddataEditing#14](../data-tools/codesnippet/CSharp/validate-data-in-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#14](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_2.vb)]

### <a name="to-get-all-changed-records-from-a-data-table"></a>데이터 테이블에서 변경 된 모든 레코드를 가져오려면

-   호출을 <xref:System.Data.DataTable.GetChanges%2A> 메서드는 DataTable입니다.

     다음 예제에서는 라는 새 데이터 테이블을 만듭니다 `changedRecordsTable` 이라는 다른 데이터 테이블에서 변경된 된 모든 레코드를 사용 하 여 채웁니다 `dataTable1`합니다.

     [!code-csharp[VbRaddataEditing#15](../data-tools/codesnippet/CSharp/validate-data-in-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#15](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_3.vb)]

### <a name="to-get-all-records-that-have-a-specific-row-state"></a>특정 행 상태에 있는 모든 레코드를 가져오려면

-   호출을 `GetChanges` 데이터 집합 및 데이터 테이블 패스는 메서드를 <xref:System.Data.DataRowState> 인수로 열거형 값입니다.

     다음 예제에서는 라는 새 데이터 집합을 만드는 방법을 보여 줍니다 `addedRecords` 에 추가 된 레코드로만 채웁니다는 `dataSet1` 데이터 집합입니다.

     [!code-csharp[VbRaddataEditing#16](../data-tools/codesnippet/CSharp/validate-data-in-datasets_4.cs)]
     [!code-vb[VbRaddataEditing#16](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_4.vb)]

     다음 예제에서는 최근에 추가 된 모든 레코드를 반환 하는 방법의 `Customers` 테이블:

     [!code-csharp[VbRaddataEditing#17](../data-tools/codesnippet/CSharp/validate-data-in-datasets_5.cs)]
     [!code-vb[VbRaddataEditing#17](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_5.vb)]

## <a name="access-the-original-version-of-a-datarow"></a>DataRow의 원래 버전에 액세스
데이터 집합 유지 모두 원래 데이터 행을 변경 하는 경우 (<xref:System.Data.DataRowVersion.Original>) 및 새 (<xref:System.Data.DataRowVersion.Current>) 행의 버전입니다. 예를 들어를 호출 하기 전에 합니다 `AcceptChanges` 메서드를 응용 프로그램 레코드의 다른 버전에 액세스할 수 (에 정의 된 대로 <xref:System.Data.DataRowVersion> 열거형) 적절 하 게 변경 내용을 처리 하 고 합니다.

> [!NOTE]
>  행의 서로 다른 버전을 편집한 후에 및 하기 전에 존재는 `AcceptChanges` 메서드가 호출 되었습니다. 이후에 `AcceptChanges` 메서드를 호출한, 현재 및 원래 버전은 동일 합니다.

전달 된 <xref:System.Data.DataRowVersion> 값 열 인덱스 (또는 열의 이름 (문자열))과 함께 해당 열의 특정 행 버전 값을 반환 합니다. 변경된 된 열 중에 식별 되는 <xref:System.Data.DataTable.ColumnChanging> 고 <xref:System.Data.DataTable.ColumnChanged> 이벤트입니다. 이 유효성 검사를 위해 다른 행 버전을 검사 하는 것이 좋습니다. 그러나 제약 조건을 일시적으로 일시 중단 한, 이러한 이벤트를 발생 하지 않습니다 및 프로그래밍 방식으로 해야 합니다 하는 경우에 열이 변경 되었는지 식별 합니다. 반복 하 여 이렇게 합니다 <xref:System.Data.DataTable.Columns%2A> 컬렉션과 다른 비교 <xref:System.Data.DataRowVersion> 값.

### <a name="to-get-the-original-version-of-a-record"></a>레코드의 원래 버전을 가져오려면

-   전달 하 여 열 값에 액세스 합니다 <xref:System.Data.DataRowVersion> 반환할 행의 합니다.

     다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Data.DataRowVersion> 의 원래 값을 검색할 값을 `CompanyName` 필드에 <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#21](../data-tools/codesnippet/CSharp/validate-data-in-datasets_6.cs)]
     [!code-vb[VbRaddataEditing#21](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_6.vb)]

## <a name="access-the-current-version-of-a-datarow"></a>DataRow의 현재 버전에 액세스

### <a name="to-get-the-current-version-of-a-record"></a>레코드의 현재 버전을 가져오려면

-   열의 값에 액세스 하 고 반환 하려는 행의 버전을 지정 하는 인덱스에는 매개 변수를 추가 합니다.

     다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Data.DataRowVersion> 의 현재 값을 검색할 값을 `CompanyName` 필드에 <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#22](../data-tools/codesnippet/CSharp/validate-data-in-datasets_7.cs)]
     [!code-vb[VbRaddataEditing#22](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_7.vb)]

## <a name="see-also"></a>참고 항목

- [Visual Studio의 데이터 세트 도구](../data-tools/dataset-tools-in-visual-studio.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 유효성 검사](/dotnet/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용 하 여 폼 유효성에 대 한 오류 아이콘 표시](/dotnet/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider)