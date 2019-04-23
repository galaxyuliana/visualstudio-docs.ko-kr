---
title: '방법: 기본 제공 탭 사용자 지정'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- built-in tabs [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5a686d2a43fed0fdb8c5c1e8f21d4b35fd63f3a6
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60075664"
---
# <a name="how-to-customize-a-built-in-tab"></a>방법: 기본 제공 탭 사용자 지정
  기본 제공 탭에 그룹과 컨트롤을 추가할 수 있습니다. 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다. 예를 들어 합니다 **데이터** 탭은 Excel에서 기본 제공 탭 합니다. 사용자 지정 그룹을 만드는 경우 탭에서 마지막에 표시되지만 탭의 아무곳으로나 그룹을 이동할 수 있습니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

> [!NOTE]
>  기본 제공 탭에 그룹을 추가할 수 있지만 기본 제공 탭에서 기본 제공 그룹을 제거할 수는 없습니다.

### <a name="to-add-groups-to-a-built-in-tab"></a>기본 제공 탭에 그룹을 추가하려면

1. 리본 코드 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**를 클릭 하 고 **뷰 디자이너**합니다.

    > [!NOTE]
    >  리본 코드 파일에 표시 되지 않으면 **솔루션 탐색기**를 추가 해야 합니다는 **리본 항목** 프로젝트입니다. [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다.

2. 리본 디자이너에서 임의 탭을 마우스 오른쪽 단추로 누른 **속성**합니다.

3. 에 **속성** 창 확장를 **ControlId** 속성을 설정 합니다 **ControlIdType** 속성을 **Office**합니다.

4. 설정 합니다 **OfficeId** 속성을 합니다 *컨트롤 ID* 사용자 지정 하려는 기본 제공 탭.

     컨트롤 ID는 Microsoft Office 응용 프로그램에 기본 제공된 탭, 그룹 및 컨트롤을 고유하게 식별하는 이름입니다.

     컨트롤 Id의 목록을 참조 하세요. [Office 2010 도움말 파일: Office fluent 사용자 인터페이스 제어 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.

5. **Office 리본 컨트롤** 탭의 **도구 상자**, 탭 그룹으로 끌어 합니다.

    > [!NOTE]
    >  기본 제공 그룹은 디자이너에 표시되지 않습니다. 따라서 기본 제공 탭을 사용 하 고 있는지 여부를 확인 하는 유일한 방법은 검사 하는 합니다 **ControlId** 탭의 속성입니다.

### <a name="to-position-groups-on-a-built-in-tab"></a>기본 제공 탭에 그룹을 배치하려면

1. 리본 디자이너에서 사용자 지정 그룹을 선택합니다.

2. 에 **속성** 창에서 확장을 **위치** 속성.

3. 설정 된 **PositionType** 속성을 적절 한 값:

    - **BeforeOfficeId** 지정된 된 기본 제공 그룹 앞에 그룹을 배치 합니다.

    - **AfterOfficeId** 지정 된 기본 제공 그룹 뒤에 그룹을 배치 합니다.

4. 설정 된 **OfficeId** 속성을 기본 제공 그룹의 컨트롤 ID입니다.

     컨트롤 Id의 목록을 참조 하세요. [Office 2010 도움말 파일: Office fluent 사용자 인터페이스 제어 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.

## <a name="see-also"></a>참고자료
- [리본 개요](../vsto/ribbon-overview.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
- [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)
- [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [방법: 추가 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)
