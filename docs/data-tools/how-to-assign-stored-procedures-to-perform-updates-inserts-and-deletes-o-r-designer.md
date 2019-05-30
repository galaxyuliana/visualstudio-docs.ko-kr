---
title: LINQ to SQL의에서 저장된 프로시저를 사용 하 여 업데이트 데이터 (O/R 디자이너)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 58dfb1016097429eeab10c3b50262adc7015e818
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "66260801"
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)

저장 프로시저를 **O/R 디자이너**에 추가하여 일반적인 <xref:System.Data.Linq.DataContext> 메서드로 실행할 수 있습니다. LINQ to SQL 런타임 동작 변경 내용을 데이터베이스에 엔터티 클래스에서 저장 되 면 삭제 및 삽입, 업데이트를 수행 하는 기본값을 재정의 하려면 사용할 수도 있습니다 (예를 들어, 호출 하는 경우를 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드).

> [!NOTE]
> 클라이언트로 다시 보내야 하는 값(예: 저장 프로시저에서 계산된 값)을 저장 프로시저에서 반환하는 경우 저장 프로시저에 출력 매개 변수를 만듭니다. 출력 매개 변수를 사용할 수 없는 경우 O/R 디자이너에서 생성된 재정의를 사용하지 말고 부분 메서드(Partial Method) 구현을 작성합니다. 데이터베이스에서 생성된 값에 매핑되는 멤버는 INSERT 또는 UPDATE 작업이 성공적으로 완료된 후 적절한 값으로 설정되어야 합니다. 자세한 내용은 [는 개발자의 기본 동작 재정의의 책임](/dotnet/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior)합니다.

> [!NOTE]
> LINQ to SQL에서 identity (자동 증분), rowguidcol (데이터베이스에서 생성 된 GUID) 및 timestamp 열에 대해 자동으로 데이터베이스에서 생성 된 값을 처리 합니다. 데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다. 데이터베이스에서 생성 된 값을 반환 하려면 직접 설정 해야 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 하 **true** 고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> 다음 중 하나에: [AutoSync.Always](<xref:System.Data.Linq.Mapping.AutoSync.Always>)하십시오 [AutoSync.OnInsert](<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>), 또는 [AutoSync.OnUpdate](<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate>)합니다.

## <a name="configure-the-update-behavior-of-an-entity-class"></a>엔터티 클래스의 업데이트 동작 구성

기본적으로 LINQ to SQL 런타임 하 여 linq에서 to SQL 엔터티 클래스 데이터에 대 한 변경 (삽입, 업데이트 및 삭제) 데이터베이스를 업데이트 하는 논리가 제공 됩니다. 런타임에서는 열 및 기본 키 정보와 같은 테이블 스키마를 기반으로 기본 INSERT, UPDATE 및 DELETE 명령을 만듭니다. 기본 동작을 원하지 않는 경우에 필요한 삽입, 업데이트 및 테이블의 데이터를 조작 하는 데 필요한 삭제를 수행 하기 위한 특정 저장된 프로시저를 할당 하 여 업데이트 동작을 구성할 수 있습니다. 엔터티 클래스가 뷰에 매핑되는 때와 같이 기본 동작이 생성되지 않은 경우에도 이렇게 할 수 있습니다. 또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>저장 프로시저를 지정하여 엔터티 클래스의 기본 동작을 재정의하려면

1. 디자이너에서 **LINQ to SQL** 파일을 엽니다. (**솔루션 탐색기**에서 **.dbml** 파일을 두 번 클릭합니다.)

2. **서버 탐색기** 또는 **데이터베이스 탐색기**에서 **저장 프로시저**를 확장하여 엔터티 클래스의 삽입, 업데이트 및/또는 삭제 명령에 사용할 저장 프로시저를 찾습니다.

3. 저장 프로시저를 **O/R 디자이너**로 끌어 놓습니다.

     저장 프로시저는 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다. 자세한 내용은 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.

4. 업데이트 수행을 위해 저장 프로시저를 사용하려는 엔터티 클래스를 선택합니다.

5. **속성** 창에서 재정의할 **삽입**, **업데이트** 또는 **삭제** 명령을 선택합니다.

6. **런타임 사용** 옆의 줄임표(...)를 클릭하여 **동작 구성** 대화 상자를 엽니다.

7. **사용자 지정**을 선택합니다.

8. **사용자 지정** 목록에서 원하는 저장 프로시저를 선택합니다.

9. **메서드 인수** 및 **클래스 속성** 목록을 살펴보고 **메서드 인수**가 적절한 **클래스 속성**에 매핑되어 있는지 확인합니다. 원래 메서드 인수 (`Original_<ArgumentName>`)를 원래 속성 (`<PropertyName> (Original)`)에 대 한 합니다 `Update` 및 `Delete` 명령입니다.

    > [!NOTE]
    > 기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다. 속성 이름이 변경되어서 더 이상 테이블과 엔터티 클래스 간에 일치하지 않으면 디자이너에서 올바른 매핑을 결정할 수 없는 경우 매핑할 해당 클래스 속성을 선택해야 합니다.

10. **확인** 또는 **적용**을 클릭합니다.

    > [!NOTE]
    > 계속으로 클릭 하면 각 클래스 및 동작 조합에 대 한 동작을 구성할 수 있습니다 **적용** 각 변경 합니다. 클릭 하기 전에 클래스 또는 동작을 변경 하는 경우 **적용**, 경고 대화 상자가 표시 되 고 변경 내용을 적용할 수 있는 기회를 제공 합니다.

업데이트의 기본 런타임 논리 사용으로 되돌아가려면 **속성** 창에서 **삽입**, **업데이트** 또는 **삭제** 명령 옆의 줄임표를 클릭한 다음, **동작 구성** 대화 상자에서 **런타임 사용**을 선택합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext 메서드](../data-tools/datacontext-methods-o-r-designer.md)
- [LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [삽입, 업데이트 및 삭제 작업 (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/insert-update-and-delete-operations)
