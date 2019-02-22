---
title: 리본 개요
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, multiple Ribbons
- Ribbon [Office development in Visual Studio], about Ribbon
- toolbars [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], multiple Ribbons
- toolbars [Office development in Visual Studio]
- custom Ribbon, multiple Ribbons
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 387ec5814e0b5a2a8c2169198a3ceebad47e10d4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599482"
---
# <a name="ribbon-overview"></a>리본 개요
  리본 메뉴 관련된 명령을 쉽게 찾을 수 있도록 구성할 수 있는 방법이 있습니다. 명령은 리본 메뉴에 컨트롤로 나타납니다. 컨트롤은으로 구성 된 *그룹* 응용 프로그램 창 위쪽 가장자리의 가로 스트립을 따라. 관련 그룹은 탭에서 구성됩니다.

 대부분의 기능은 메뉴 및 도구 모음을 사용 하 여 이전 버전의 Microsoft Office 시스템에서 액세스 한 리본 메뉴를 사용 하 여 액세스할 수 있습니다. 자세한 내용은 기술 문서를 참조 하십시오. [개발자 개요 2007 Microsoft Office system 사용자 인터페이스의](http://go.microsoft.com/fwlink/?LinkID=70860).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

## <a name="customize-the-microsoft-office-ribbon"></a>Microsoft Office 리본을 사용자 지정
 리본 메뉴를 사용자 지정 하려면 Office 프로젝트에 다음 리본 항목 중 하나를 추가 합니다.

- **리본 (비주얼 디자이너)**

- **리본 (XML)**

  예를 들어 Excel 리본을 사용자 지정하려면 Excel VSTO 추가 기능 프로젝트에 리본 항목을 추가합니다.

### <a name="ribbon-visual-designer-item"></a>리본 (비주얼 디자이너) 항목
 **리본 (비주얼 디자이너)** 항목은 쉽게 디자인 하 고 사용자 지정 리본 메뉴를 개발할 수 있는 고급 도구를 제공 합니다. 사용 하는 **리본 (비주얼 디자이너)** 다음과 같은 방법으로 리본 메뉴를 사용자 지정할 수 있는 항목:

- 리본 메뉴에 사용자 지정 또는 기본 제공 탭을 추가 합니다.

- 사용자 지정 또는 기본 제공 탭에 사용자 지정 그룹을 추가합니다.

  > [!NOTE]
  >  기본 제공 탭 이나 그룹은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있습니다. 예를 들어 합니다 **데이터** 탭은 Excel에서 기본 제공 탭 합니다. **연결** 그룹은 기본 제공 그룹에는 **데이터** 탭.

- 사용자 지정 그룹에 사용자 지정 컨트롤을 추가합니다.

- Backstage 보기에 사용자 지정 컨트롤을 추가합니다.

  사용 하 여 리본 메뉴를 사용자 지정 하는 방법에 대 한 자세한 내용은 해당 **리본 (비주얼 디자이너)** 항목을 참조 하십시오. [리본 디자이너](../vsto/ribbon-designer.md).

### <a name="ribbon-xml-item"></a>리본 (XML) 항목
 사용 하는 **리본 (XML)** 항목에서 지원 되지 않는 방식으로 리본 메뉴를 사용자 지정 하려는 경우는 **리본 (비주얼 디자이너)** 항목입니다. 사용 하는 **리본 (XML)** 다음과 같은 방법으로 리본 메뉴를 사용자 지정할 수 있는 항목:

- 추가 *기본 제공* 그룹을 사용자 지정 탭 이나 기본 제공 탭입니다.

- 사용자 지정 그룹에 기본 제공 컨트롤을 추가합니다.

- 사용자 지정 코드를 추가하여 기본 제공 컨트롤의 이벤트 처리기를 재정의합니다.

- 빠른 실행 도구 모음 사용자 지정

- 정규화된 ID를 사용하여 VSTO 추가 기능 간에 리본 사용자 지정을 공유합니다.

  사용 하 여 리본을 사용자 지정 하는 방법에 대 한 자세한 내용은 해당 **리본 (XML)** 항목을 참조 하십시오. [리본 XML](../vsto/ribbon-xml.md).

## <a name="export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>리본 디자이너에서 리본 XML로 리본 메뉴 내보내기
 리본 디자이너를 사용 하 여 리본 메뉴를 만든 경우 다음 방법으로 리본 메뉴를 사용자 지정할 것인지를 결정 하는 **리본 (비주얼 디자이너)** 항목을 지원 하지 않습니다, 리본 메뉴를 XML로 내보낼 수 있습니다.

 Visual Studio 자동으로 생성 한 **리본 (XML)** 항목을 리본 XML 파일 요소와 특성을 사용 하 여 리본 메뉴의 각 컨트롤을 채웁니다.

 에 있는 속성 중 일부는 **속성이** 리본 디자이너 창 리본 XML 파일에 전송 됩니다.  예를 들어, Visual Studio 내보내지 않습니다의 값은 **이미지** 또는 **텍스트** 속성입니다. 이는 이미지를 할당하거나 컨트롤의 텍스트를 설정하려면 내보낸 프로젝트의 리본 코드 파일에서 콜백 메서드를 만들어야 하기 때문입니다. Visual Studio는 내보내기 프로세스의 일부로 콜백 메서드를 자동으로 생성하지 않습니다.

 또한 변경되지 않은 기본 속성 값은 결과 리본 XML 파일에 표시되지 않습니다.

 XML로 리본 내보내기 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 리본 XML로 리본 디자이너에서 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)합니다.

### <a name="update-the-code"></a>코드 업데이트
 새 리본 코드 파일에 추가 됩니다 **솔루션 탐색기**. 이 파일에는 리본 XML 클래스가 포함되어 있습니다. 단추 클릭과 같은 사용자 동작을 처리하려면 이 클래스의 `Ribbon Callbacks` 영역에 콜백 메서드를 만들어야 합니다. 이벤트 처리기의 코드를 이러한 콜백 메서드로 이동하고 리본 확장성(RibbonX) 프로그래밍 모델을 사용하도록 코드를 수정합니다. 자세한 내용은 [Ribbon XML](../vsto/ribbon-xml.md)을 참조하세요.

 또한 `CreateRibbonExtensibilityObject` 메서드를 재정의하고 Office 응용 프로그램에 리본 XML 클래스를 반환하는 코드를 `ThisAddIn`, `ThisWorkbook` 또는 `ThisDocument` 클래스에 추가해야 합니다.

 자세한 내용은 [Ribbon XML](../vsto/ribbon-xml.md)을 참조하세요.

## <a name="add-multiple-ribbon-items-to-a-project"></a>프로젝트에 여러 개의 리본 항목 추가
 단일 프로젝트에 둘 이상의 리본 항목을 추가할 수 있습니다. 이 기능은 다음 두 작업 중 하나를 수행하려는 경우에 유용합니다.

-   Outlook 용 리본 만들기 *검사기*. 자세한 내용은 [Outlook에 대 한 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)합니다.

    > [!NOTE]
    >  검사기는 사용자가 메일 메시지 만들기와 같은 특정 작업을 수행할 때 열리는 창입니다.

-   런타임에 표시할 리본 메뉴를 선택 합니다.

### <a name="select-which-ribbons-to-display-at-runtime"></a>런타임에 표시할 리본을 선택 합니다.
 프로젝트에서 여러 개의 리본 메뉴를 포함할 수 있으므로 런타임에 표시할 리본 메뉴를 선택할 수 있습니다.

 런타임에 표시할 리본 메뉴를 선택 하는 `CreateRibbonExtensibilityObject` 메서드에서 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 클래스 프로젝트 및 리본 메뉴를 표시 하려면 반환 합니다. 다음 예제에서는 명명 된 필드의 값을 확인 `myCondition` 적절 한 리본 메뉴를 반환 합니다.

> [!NOTE]
>  이 예제에 사용 된 구문을 사용 하 여 만든 리본 메뉴를 반환 하면 **리본 (비주얼 디자이너)** 항목. 사용 하 여 만들어진 리본 메뉴를 반환 하는 구문은 **리본 (XML)** 항목은 약간 다릅니다. 반환 하는 방법에 대 한 자세한 내용은 **리본 (XML)** 항목을 참조 하십시오 [리본 XML](../vsto/ribbon-xml.md)합니다.

 다음 코드를 추가합니다.

 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.cs#1)]

### <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)|Microsoft Office 응용 프로그램의 리본 사용자 지정을 추가 하는 방법을 보여 줍니다 한 **리본 (비주얼 디자이너)** 또는 **리본 (XML)** 항목을 Office 프로젝트.|
|[리본 디자이너](../vsto/ribbon-designer.md)|Microsoft Office 응용 프로그램의 리본 메뉴에 사용자 지정 탭, 그룹 및 컨트롤을 추가 하 여 리본 디자이너를 사용 하는 방법을 설명 합니다.|
|[연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|리본 디자이너를 사용하여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다. 리본 디자이너를 사용하여 사용자 지정 탭에 컨트롤을 추가하고 배치할 수 있습니다.|
|[리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)|런타임에 리본 컨트롤의 속성을 설정 하 고 가져오는 데 사용할 수 있는 강력한 형식의 개체 모델에 대 한 개요를 제공 합니다.|
|[연습: 런타임에 리본의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)|리본이 Office 애플리케이션에 로드된 후 리본 개체 모델을 사용하여 리본 메뉴의 컨트롤을 업데이트하는 방법을 보여 줍니다.|
|[Outlook의 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)|Microsoft Office Outlook 리본 메뉴를 사용자 지정 하기 위한 지침을 제공 합니다.|
|[InfoPath 용 리본 사용자 지정](../vsto/customizing-a-ribbon-for-infopath.md)|Microsoft Office InfoPath에서 리본 메뉴를 사용자 지정 하기 위한 지침을 제공 합니다.|
|[런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)|표시, 숨기기, 리본, 수정 및 사용자가 컨트롤에 사용자 지정 작업 창, 작업 창 또는 양식 영역을 Outlook에서 코드를 실행할 수 있도록 하는 방법을 보여 줍니다.|
|[방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)|리본 메뉴의 탭 순서를 변경 하는 방법을 보여 줍니다.|
|[방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)|기본 제공 탭에 그룹 및 컨트롤을 추가하는 방법을 보여 줍니다.|
|[방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)|컨트롤을 클릭할 때 열리는 메뉴를 추가 하는 방법을 보여 줍니다 있는 **파일**.|
|[방법: 리본 그룹에 대화 상자 표시 아이콘 추가](../vsto/how-to-add-a-dialog-box-launcher-to-a-ribbon-group.md)|리본 메뉴의 그룹에 대화 상자 표시 아이콘을 추가할 수 보여 줍니다.|
|[방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)|하 여 디자이너에서 리본 XML로 내보내어 고급 방식으로 리본을 사용자 지정 하는 방법을 보여 줍니다.|
|[Ribbon XML](../vsto/ribbon-xml.md)|리본 메뉴를 사용자 지정 리본 메뉴 XML을 사용 하 여 방법에 대해 설명 합니다.|
|[연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|사용 하 여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다 있는 **리본 (XML)** 항목입니다.|
