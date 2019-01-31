---
title: 매개 변수가 있는 TableAdapter 쿼리 만들기
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: a65b8cbffaefff340297e80f708fa74abe352e6d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037644"
---
# <a name="create-parameterized-tableadapter-queries"></a>매개 변수가 있는 TableAdapter 쿼리 만들기

매개 변수가 있는 쿼리는 쿼리의 WHERE 절 조건을 충족하는 데이터를 반환합니다. 예를 들어 고객 목록을 반환하는 SQL 문 끝에 `WHERE City = @City`를 추가하여 특정 구/군/시의 고객만 표시하도록 고객 목록을 매개 변수화할 수 있습니다.

매개 변수가 있는 TableAdapter 쿼리를 만드는 합니다 **데이터 집합 디자이너**합니다. 사용 하 여 Windows 응용 프로그램에서 만들 수 있습니다는 **데이터 소스 매개 변수화** 명령 합니다 **데이터** 메뉴. 합니다 **데이터 소스 매개 변수화** 명령 매개 변수 값을 입력 하 고 쿼리를 실행할 수 있는 폼의 컨트롤을 만듭니다.

> [!NOTE]
> 매개 변수가 있는 쿼리를 생성 하는 경우에 대 한 코딩 하는 데이터베이스에 관련 된 매개 변수 표기법을 사용 합니다. 예를 들어 Access 및 OleDb 데이터 소스는 물음표 '?'를 사용하여 매개 변수를 표기하므로 WHERE 절은 `WHERE City = ?`와 같습니다.

## <a name="create-a-parameterized-tableadapter-query"></a>매개 변수가 있는 TableAdapter 쿼리 만들기

### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>데이터 집합 디자이너에서 매개 변수가 있는 쿼리를 만들려면

-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 새 TableAdapter를 만듭니다. 자세한 내용은 [만들기 및 Tableadapter 구성](../data-tools/create-and-configure-tableadapters.md)합니다.

     또는

-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 기존 TableAdapter에 쿼리를 추가합니다.

### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>데이터 바인딩된 폼을 디자인하면서 매개 변수가 있는 쿼리를 만들려면

1.  데이터 집합에 이미 바인딩되어 있는 폼의 컨트롤을 선택합니다. 자세한 내용은 [Visual Studio에서 데이터 바인딩 Windows Forms 컨트롤](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)합니다.

2.  에 **데이터** 메뉴에서 **쿼리 추가**합니다.

3.  원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 **검색 조건 작성기** 대화 상자에서 필요한 작업을 완료합니다.

### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>기존 데이터 바인딩된 폼에 쿼리를 추가하려면

1.  **Windows Forms 디자이너**에서 폼을 엽니다.

2.  에 **데이터** 메뉴에서 **쿼리 추가** 또는 **데이터 스마트 태그**합니다.

    > [!NOTE]
    > **데이터** 메뉴에서 **쿼리 추가**를 사용할 수 없는 경우 매개 변수화를 추가할 데이터 소스가 표시되어 있는 폼의 컨트롤을 선택합니다. 예를 들어 폼의 <xref:System.Windows.Forms.DataGridView> 컨트롤에 데이터가 표시되는 경우 해당 컨트롤을 선택합니다. 폼의 개별 컨트롤에 데이터가 표시되는 경우에는 데이터 바인딩된 컨트롤을 선택합니다.

3.  에 **선택한 데이터 원본 테이블** 영역에서 매개 변수화를 추가 하려는 테이블을 선택 합니다.

4.  새 쿼리를 만드는 경우 **새 쿼리 이름** 상자에 이름을 입력합니다.

     또는

     **기존 쿼리 이름** 상자에서 쿼리를 선택합니다.

5.  에 **쿼리 텍스트** 상자, 매개 변수를 사용 하는 쿼리를 입력 합니다.

6.  **확인**을 선택합니다.

     매개 변수를 입력하기 위한 컨트롤과 **로드** 단추가 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 폼에 추가됩니다.

### <a name="query-for-null-values"></a>Null 값에 대 한 쿼리

TableAdapter 매개 변수가 현재 값이 없는 레코드를 쿼리 하려는 경우 null 값 할당할 수 있습니다. 예를 들어 포함 된 다음 쿼리에 `ShippedDate` 매개 변수에서 해당 `WHERE` 절:

 ```sql
SELECT CustomerID, OrderDate, ShippedDate
FROM Orders
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```

TableAdapter에 대 한 쿼리 인 경우 다음 코드를 사용 하 여 운송 하지 않았다고 하는 모든 주문에 대해 쿼리할 수 있습니다.

[!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
[!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]

Null 값을 허용 하도록 쿼리를 사용할 수 있도록 합니다.

1.  에 **데이터 집합 디자이너**, null 매개 변수 값을 허용 해야 하는 TableAdapter 쿼리를 선택 합니다.

2.  에 **속성** 창에서 **매개 변수**, 줄임표를 클릭 한 다음 (**...** ) 버튼을 클릭 하 여 **매개 변수 컬렉션 편집기**합니다.

3.  Null 값을 허용 하는 매개 변수를 선택 하 고 설정 합니다 **AllowDbNull** 속성을 `true`입니다.

## <a name="see-also"></a>참고 항목

- [TableAdapter를 사용하여 데이터 세트 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)