---
title: O/R 디자이너 개요
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 4105a93d4ad459c8bc1cb3a7a20b37c69f311c12
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62566422"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>Visual Studio의 LINQ to SQL 도구

LINQ to SQL 첫 번째 개체-관계형 매핑 기술을 Microsoft에서 출시 되었습니다. 기본 시나리오에서 잘 작동 하며 Visual Studio에서 지원 되는 데 계속 이지만 더 이상 개발 합니다. LINQ to SQL을 이미 사용 되는 레거시 응용 프로그램을 유지 관리 하는 경우 또는 다중 테이블 매핑이 필요 하지 않습니다 및 SQL Server를 사용 하는 간단한 응용 프로그램을 사용 합니다. 일반적으로 새 응용 프로그램 개체 관계형 매퍼 레이어를 필요할 때 Entity Framework를 사용 해야 합니다.

Visual Studio에서 만든 LINQ to SQL 클래스를 사용 하 여 SQL 테이블을 나타내는 합니다 **Object Relational Designer** (**O/R 디자이너**).

합니다 **O/R 디자이너** 에 디자인 화면에서 두 개의 고유 영역: 엔터티 창 왼쪽 및 오른쪽에는 메서드 창이 있습니다. 엔터티 창은 엔터티 클래스, 연결 및 상속 계층을 표시하는 기본 디자인 화면입니다. 메서드 창은 저장 프로시저와 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드를 표시하는 디자인 화면입니다.

합니다 **O/R 디자이너** 시각적 디자인 화면을 만들기 위한 제공 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 엔터티 클래스 및 데이터베이스의 개체를 기반으로 하는 연결 (관계). 즉, 합니다 **O/R 디자이너** 데이터베이스의 개체에 매핑되는 응용 프로그램에서 개체 모델을 만듭니다. 또한 강력한 형식의 생성 <xref:System.Data.Linq.DataContext> 엔터티 클래스와 데이터베이스 간에 데이터를 송수신 하는 합니다. 합니다 **O/R 디자이너** 저장된 프로시저를 매핑하는 기능을 제공 하 고 함수를 <xref:System.Data.Linq.DataContext> 메서드 데이터를 반환 하 고 엔터티 클래스를 채우기입니다. 마지막으로, 합니다 **O/R 디자이너** 엔터티 클래스 간의 상속 관계를 디자인 하는 기능을 제공 합니다.

## <a name="open-the-or-designer"></a>O/R 디자이너 열기

LINQ to SQL 엔터티 모델 프로젝트를 추가 하려면 **프로젝트** > **새 항목 추가**를 선택한 후 **LINQ to SQL 클래스** 프로젝트 항목의 목록에서:

![LINQ to SQL 클래스](../data-tools/media/raddata-linq-to-sql-classes.png)

Visual Studio 만듭니다는 *.dbml* 파일을 솔루션에 추가 합니다. 이것은 XML 매핑 파일 및 해당 관련된 코드 파일입니다.

![LINQ to SQL 클래스 솔루션 탐색기에서](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png)

선택 하는 경우는 *.dbml* 파일을 Visual Studio에 표시를 **O/R 디자이너** 화면을 시각적으로 모델을 만들 수 있도록 합니다. 다음 그림에서는 Northwind 후 디자이너를 보여 줍니다 `Customers` 하 고 `Orders` 테이블에서 끌어 놓았을 **서버 탐색기**합니다. 테이블 간의 관계를 note 합니다.

![LINQ to SQL 디자이너](../data-tools/media/raddata-linq-to-sql-designer.png)

> [!IMPORTANT]
> 합니다 **O/R 디자이너** 1:1 매핑 관계만 지 원하는 단순 개체 관계형 매퍼입니다. 즉, 엔터티 클래스는 데이터베이스 테이블 또는 뷰와 1:1 매핑 관계만 갖습니다. 엔터티 클래스가 조인 된 테이블에 매핑할 복잡 한 매핑은 지원 되지 않습니다. 복잡 한 매핑에 대 한 Entity Framework를 사용 합니다. 또한 이 디자이너는 단방향 코드 생성기입니다. 이는 디자이너 화면에서 변경한 내용만이 코드 파일에 반영된다는 의미입니다. 코드 파일에 수동으로 변경한 내용은에 반영 되지 않습니다 합니다 **O/R 디자이너**합니다. 코드 파일에서 수동으로 변경한 모든 내용은 디자이너를 저장하고 코드를 다시 생성할 때 덮어쓰여집니다. 사용자 코드를 추가 하 여 생성 된 클래스를 확장 하는 방법에 대 한 자세한 합니다 **O/R 디자이너**를 참조 하세요 [방법: O/R 디자이너에서 생성 된 코드 확장](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)합니다.

## <a name="create-and-configure-the-datacontext"></a>만들고 DataContext 구성

추가한 후를 **LINQ to SQL 클래스** 프로젝트를 열고 항목은 **O/R 디자이너**, 빈 디자인 화면을 나타내는 빈 <xref:System.Data.Linq.DataContext> 구성 가능한 상태가 됩니다. 따라서 <xref:System.Data.Linq.DataContext>는 디자인 화면에 놓여진 첫째 항목에서 제공된 연결 정보를 사용하여 구성됩니다. 따라서 <xref:System.Data.Linq.DataContext>는 디자인 화면에 놓여진 첫째 항목의 연결 정보를 사용하여 구성됩니다. 에 대 한 자세한 내용은 합니다 <xref:System.Data.Linq.DataContext> 클래스 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.

## <a name="create-entity-classes-that-map-to-database-tables-and-views"></a>데이터베이스 테이블 및 뷰에 매핑되는 엔터티 클래스 만들기

데이터베이스 테이블 및 뷰를 끌어 테이블 및 뷰에 매핑된 엔터티 클래스를 만들 수 있습니다 **서버 탐색기** 하거나 **데이터베이스 탐색기** 에 **O/R 디자이너**합니다. 이전 섹션에서 설명한 것처럼 <xref:System.Data.Linq.DataContext>는 디자인 화면으로 끌어온 첫 번째 항목에서 제공된 연결 정보를 사용하여 구성됩니다. 다른 연결을 사용 하는 후속 항목에 추가 됩니다는 **O/R 디자이너**에 대 한 연결을 변경할 수는 <xref:System.Data.Linq.DataContext>합니다. 자세한 내용은 [방법: 테이블 및 보기에 매핑된 LINQ to SQL 클래스 만들기(O/R 디자이너)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)를 참조하세요.

## <a name="create-datacontext-methods-that-call-stored-procedures-and-functions"></a>저장된 프로시저 및 함수를 호출 하는 DataContext 메서드 만들기

만들 수 있습니다 <xref:System.Data.Linq.DataContext> 메서드를 호출 하는 (매핑됩니다) 저장 프로시저 및 함수에서 끌어서 **서버 탐색기** 하거나 **데이터베이스 탐색기** 에 **O/R 디자이너** . 저장된 프로시저 및 함수에 추가 되는 **O/R 디자이너** 의 메서드로 <xref:System.Data.Linq.DataContext>합니다.

> [!NOTE]
> 저장된 프로시저 및 함수를 끌어 오면 **서버 탐색기** 또는 **데이터베이스 탐색기** 에 **O/R 디자이너**, 생성 된 반환 형식은 <xref:System.Data.Linq.DataContext> 메서드는 항목을 놓는 위치에 따라 다릅니다. 자세한 내용은 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.

## <a name="configure-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>엔터티 클래스와 데이터베이스 간에 데이터를 저장 하려면 저장된 프로시저를 사용 하도록 DataContext 구성

앞에서 설명한 대로 저장 프로시저 및 함수를 호출하는 <xref:System.Data.Linq.DataContext> 메서드를 만들 수 있습니다. 또한 기본 LINQ to SQL 런타임 동작을 수행 하는 삽입, 업데이트 및 삭제에 사용 되는 저장된 프로시저를 할당할 수 있습니다. 자세한 내용은 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)을 참조하세요.

## <a name="inheritance-and-the-or-designer"></a>상속 및 O/R 디자이너

다른 개체와 마찬가지로 LINQ to SQL 클래스 상속을 사용할 수 및 다른 클래스에서 파생 되어야 합니다. 데이터베이스에서 상속 관계는 여러 가지 방법으로 만들어집니다. 합니다 **O/R 디자이너** 관계형 시스템에서 주로 구현 되는 단일 테이블 상속 개념을 지원 합니다. 자세한 내용은 [방법: O/R 디자이너를 사용하여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)을 참조하세요.

## <a name="linq-to-sql-queries"></a>LINQ to SQL 쿼리

만드는 엔터티 클래스를 **O/R 디자이너** 사용 하 여 사용 하도록 디자인 되었습니다 [언어 통합 쿼리 (LINQ)](/dotnet/csharp/linq/)합니다. 자세한 내용은 [방법: 정보에 대 한 쿼리](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information)합니다.

## <a name="separate-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>생성 된 DataContext와 엔터티 클래스 코드를 다른 네임 스페이스로 분리

**O/R 디자이너** 제공 합니다 **상황에 맞는 Namespace** 및 **엔터티 Namespace** 속성에는 <xref:System.Data.Linq.DataContext>합니다. 이들 속성은 <xref:System.Data.Linq.DataContext> 및 엔터티 클래스 코드가 어떤 네임스페이스로 생성되는지를 결정합니다. 기본적으로 이들 속성은 비어 있으며 <xref:System.Data.Linq.DataContext> 및 엔터티 클래스는 응용 프로그램의 네임스페이스로 생성됩니다. 코드를 애플리케이션의 네임스페이스가 아닌 다른 네임스페이스로 생성하려면 **컨텍스트 네임스페이스** 및/또는 **엔터티 네임스페이스** 속성에 값을 입력합니다.

## <a name="reference-content"></a>참조 콘텐츠

- <xref:System.Linq>
- <xref:System.Data.Linq>

## <a name="see-also"></a>참고자료

- [LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [질문과 대답 (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions)