---
title: TableAdapter를 사용하여 데이터 업데이트
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: ca5161d0ddb73a72b88f36e85bda9206839aec3d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565862"
---
# <a name="update-data-by-using-a-tableadapter"></a>TableAdapter를 사용하여 데이터 업데이트

데이터 집합의 데이터를 수정 하 고 유효성을 검사 된 후 보낼 수 있습니다 업데이트 된 데이터를 데이터베이스에 다시 호출 하 여 합니다 `Update` 메서드를 [TableAdapter](../data-tools/create-and-configure-tableadapters.md)합니다. `Update` 메서드는 단일 데이터 테이블을 업데이트 하 고 올바른 명령을 (INSERT, UPDATE 또는 DELETE)에 따라 실행을 <xref:System.Data.DataRow.RowState%2A> 테이블의 각 데이터 행입니다. 데이터 집합에 관련 테이블, Visual Studio는 업데이트를 수행 하는 데 사용할 수 있는 TableAdapterManager 클래스를 생성 합니다. TableAdapterManager 클래스는 데이터베이스에 정의 된 외래 키 제약 조건에 따라 올바른 순서로 업데이트를 확인 합니다. 데이터 바인딩된 컨트롤을 사용 하면 데이터 바인딩 아키텍처 tableAdapterManager 호출 되는 TableAdapterManager 클래스의 멤버 변수를 만듭니다.

> [!NOTE]
> 데이터 집합의 콘텐츠를 사용 하 여 데이터 소스를 업데이트 하려고 할 때 오류를 가져올 수 있습니다. 오류를 방지 하려면 어댑터를 호출 하는 코드를 추가 하는 권장 `Update` 내에서 메서드를 `try` / `catch` 블록입니다.

 데이터 소스를 업데이트 하기 위한 정확한 절차는 비즈니스 요구 사항에 따라 달라질 수 있지만 다음 단계가 포함 됩니다.

1. 어댑터의 호출 `Update` 의 메서드를 `try` / `catch` 블록입니다.

2. 예외가 포착 되는 경우 오류를 발생 시키는 데이터 행을 찾습니다.

3. 데이터의 문제 (가능한 경우 프로그래밍 방식으로 또는 수정에 대 한 사용자에 게 잘못 된 행을 제공 하 여) 행을 한 다음 다시 업데이트 (<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>).

## <a name="save-data-to-a-database"></a>데이터베이스에 데이터를 저장 합니다.

호출 된 `Update` TableAdapter의 메서드. 데이터베이스에 쓸 값이 포함 된 데이터 테이블의 이름을 전달 하세요.

### <a name="to-update-a-database-by-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터베이스를 업데이트 하려면

- TableAdapter의 묶습니다`Update` 의 메서드를 `try` / `catch` 블록입니다. 다음 예제에서는의 내용을 업데이트 하는 방법을 보여 줍니다 합니다 `Customers` 테이블의 `NorthwindDataSet` 내에서 `try` / `catch` 블록입니다.

     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]

## <a name="see-also"></a>참고자료

- [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)