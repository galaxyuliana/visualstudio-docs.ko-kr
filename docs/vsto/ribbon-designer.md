---
title: 리본 디자이너
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, about Ribbon Designer
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- customizing the Ribbon, about Ribbon Designer
- Ribbon [Office development in Visual Studio], visual designer
- customizing the Ribbon
- custom Ribbon
- designers [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon [Office development in Visual Studio], common tasks
- Ribbon Designer [Office development in Visual Studio]
- read-only properties
- Ribbon [Office development in Visual Studio], shortcut keys
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8cc47445f9d2024f5d8a83c8f376bc0299b8ea4e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60103643"
---
# <a name="ribbon-designer"></a>리본 디자이너
  리본 디자이너는 시각적 디자인 캔버스입니다. Microsoft Office 응용 프로그램의 리본에 사용자 지정 탭, 그룹 및 컨트롤을 추가 하려면 리본 디자이너를 사용 합니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

 리본 디자이너를 열려면 추가 **리본 (비주얼 디자이너)** 프로젝트 항목입니다. 그런 다음 다음과 같은 작업에 대 한 디자인 도구를 사용할 수 있습니다.

- [리본 메뉴 레이아웃 디자인](#DesigningRibbonLayout)

- [이벤트를 처리 하 고 컨트롤 속성 설정](#HandleEventsSetProperties)

- [Backstage 보기에 컨트롤 추가](#CustomizingMicrosoftOfficeButton)

> [!NOTE]
>  리본 디자이너를 사용 하 여 수행할 수 없는 작업도 있습니다. 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [리본 개요](../vsto/ribbon-overview.md)합니다.

 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? Outlook에서 리본을 사용자 지정 리본 디자이너 사용 ](http://go.microsoft.com/fwlink/?LinkID=130312).

## <a name="add-a-ribbon-visual-designer-item-to-a-project"></a>리본 (비주얼 디자이너) 항목을 프로젝트에 추가
 리본 디자이너를 사용 하려면 새 추가 **리본 (비주얼 디자이너)** 프로젝트 항목입니다. 자세한 내용은 [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다.

 새로 추가한 경우 **리본 (비주얼 디자이너)** 항목, Visual Studio에 자동으로 추가 다음 파일이 프로젝트:

- 리본 코드 파일. 이 파일에 지정 하는 이름에는 **리본 (비주얼 디자이너)** 항목에 **새 항목 추가** 대화 상자. 이 파일에 리본 이벤트를 처리 하는 코드를 추가 합니다.

- 리본 디자이너 코드 파일입니다. 이 파일에는 리본 디자이너에서 생성 된 코드를 포함 하며 직접 편집할 수 없습니다.

- 리소스 파일입니다. 이 파일에 리본 메뉴에 있는 각 컨트롤의 속성 값을 포함합니다.

  이미 있는 경우는 **리본 (비주얼 디자이너)** 항목 다른 프로젝트에서 다시 사용할 수 있습니다 현재 프로젝트에서 사용 하 여 합니다 **기존 항목 추가** 대화 상자.

## <a name="DesigningRibbonLayout"></a> 리본 메뉴 디자인
 리본 디자이너를 여는 방법은 세 가지가 있습니다.

- **솔루션 탐색기**, 리본 코드 파일을 두 번 클릭 합니다.

- **솔루션 탐색기**리본 코드 파일을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **뷰 디자이너**합니다.

- **솔루션 탐색기**리본 코드 파일을 선택한 다음 클릭 **디자이너** 에 **뷰** 메뉴.

  리본 디자이너에는 기본 탭 및 그룹이 포함 되어 있습니다. 리본 디자이너에서 기본 탭 및 그룹을 제거할 수 있습니다. 기본 그룹을 제거 하려면 마우스 오른쪽 단추로 클릭 **Group1**를 클릭 하 고 **삭제**합니다. 기본 탭을 제거 하려면 디자인 화면의 빈 영역을 마우스 오른쪽 단추로 클릭 하 고 클릭 **리본 탭 제거**합니다.

  또한 리본 디자이너에 사용자 지정 탭, 그룹 및 컨트롤을 추가할 수 있습니다. 이러한 컨트롤을 찾을 수는 **도구 상자**를 **Office 리본 컨트롤** 그룹입니다. 컨트롤을 추가 하는 방법은 세 가지가 있습니다 합니다 **Office 리본 컨트롤** 리본 디자이너로 그룹:

- 리본 디자이너에서 적절 한 영역 컨트롤을 끌어옵니다.

- 컨트롤을 클릭 하 고 리본 디자이너에서 적절 한 영역을 클릭 합니다.

- 디자이너에서 적절 한 영역을 선택 하 고 컨트롤을 두 번 클릭 합니다 **도구 상자**합니다.

### <a name="ribbon-design-workflow"></a>리본 디자인 워크플로
 리본 레이아웃을 디자인 하려면 다음 기본 단계를 수행 합니다.

1. [리본에 사용자 지정 탭 추가](#AddTabToRibbon)합니다.

2. [탭 그룹에 추가할](#AddGroupsToTab)합니다.

3. [컨트롤 그룹을 추가할](#AddControlsToGroups)합니다.

   컨트롤 그룹에만 삭제할 수 있습니다. 리본 메뉴 또는 탭에 직접 컨트롤을 끌 수 없습니다. 그룹 탭; 에서만 삭제할 수 있습니다. 리본 메뉴에는 직접 그룹을 끌 수 없습니다.

   올바른 위치로 드래그 하 여 컨트롤을 정렬 합니다. 사용 하 여 컨트롤의 속성을 설정할 수는 **속성** 창입니다.

   컨트롤을 리본 메뉴에서 다른 탭에서 끌어올 수 없습니다. 있습니다. 컨트롤을 다른 탭으로 이동 하려는 경우 사용 해야 합니다 **잘라내기** 한 탭에서 컨트롤을 제거 하는 컨트롤을 다른 탭에 붙여 명령입니다. 컨트롤을 잘라내어 붙여 수행, 이벤트 처리기에 작동이 중지 됩니다. 이벤트 처리기를 다시 연결할 수 있습니다 합니다 **속성** 창입니다. 자세한 내용은 [속성 창](../ide/reference/properties-window.md)합니다.

### <a name="AddTabToRibbon"></a> 리본에 사용자 지정 탭 추가
 리본에 사용자 지정 탭을 추가 하는 방법은 세 가지가 있습니다.

- 탭을 추가 합니다 **도구 상자**합니다.

- 리본 디자이너를 마우스 오른쪽 단추로 누른 **리본 탭 추가**합니다.

- 엽니다는 **탭 컬렉션 편집기**를 클릭 하 고 **추가**합니다.

   열려는 **탭 컬렉션 편집기**의 **속성** 창에서를 **탭** 속성을 다음 줄임표 단추를 클릭 하 고 ![ASP.NET 모바일 디자이너 타원](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")합니다.

  탭에 추가한 후 컨트롤을 포함할 그룹을 추가할 수 있습니다.

#### <a name="remove-custom-tabs-from-the-ribbon"></a>리본 메뉴에서 사용자 지정 탭 제거
 리본 메뉴에서 사용자 지정 탭을 제거 하는 방법은 세 가지가 있습니다.

- 디자이너를 마우스 오른쪽 단추로 누른 **리본 탭 제거**합니다.

- 에 **명령** 창 합니다 **속성** 창 클릭 **리본 탭 제거**합니다.

- 엽니다는 **탭 컬렉션 편집기**탭을 선택한 다음 클릭 **제거**합니다.

#### <a name="change-the-position-of-a-tab-on-the-ribbon"></a>리본의 탭 위치 변경
 리본 메뉴의 사용자 지정 탭 순서를 변경할 수 있습니다. 리본의 기본 제공 탭 앞 이나 뒤에 사용자 지정 탭을 배치할 수 있습니다. 자세한 내용은 [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)합니다.

#### <a name="customize-built-in-tabs-on-the-ribbon"></a>리본의 기본 제공 탭 사용자 지정
 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다. 예를 들어 합니다 **데이터** 탭은 Excel에서 기본 제공 탭 합니다.

 기본 제공 탭에 그룹과 컨트롤을 추가할 수 있습니다. 기본적으로 사용자 지정 그룹으로 이동할 수 있습니다이 모든 기본 제공 그룹 이전 또는 이후에 탭 있지만 기본 제공 탭에 있는 마지막 그룹으로 나타납니다.

 기본 제공 그룹을 제거할 수 없습니다.

 기본 제공 탭 사용자 지정 하는 방법에 대 한 세부 정보를 참조 하세요. [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)합니다.

### <a name="AddGroupsToTab"></a> 탭 그룹을 추가 합니다.
 그룹 리본 메뉴의 컨트롤을 논리적으로 구성합니다. 탭 그룹을 추가 합니다. 그룹에 다른 모든 컨트롤을 추가 합니다.

### <a name="AddControlsToGroups"></a> 그룹에 컨트롤 추가
 그룹에 하나 이상의 컨트롤을 추가 합니다. 다음 표에서 각 컨트롤을 보여 줍니다.

|컨트롤|설명|
|-------------|-----------------|
|**Object^**|그룹의 컨트롤을 구성 하는 컨테이너입니다. 구분 기호, 그룹 또는 탭을 제외 하 고 상자에 컨트롤을 추가할 수 있습니다. 상자는 가로 또는 세로 수 있습니다.|
|**Button**|액션을 시작 하는 단추입니다. 그룹, 단추 그룹, 드롭다운 목록, 갤러리, 메뉴 또는 분할 단추에 단추를 추가할 수 있습니다.|
|**ButtonGroup**|하나 이상의 단추, 설정/해제 단추, 메뉴, 분할 단추 및 갤러리가 포함 된 그룹입니다. 그룹 또는 메뉴에 단추 그룹을 추가할 수 있습니다.|
|**CheckBox**|선택 하거나 켜기 / 끄기 옵션을 선택 취소 하는 상자입니다.|
|**ComboBox**|연결 된 목록 상자를 사용 하 여 편집 상자입니다. 사용자가 입력 하거나 해당 항목을 선택 합니다. 현재 선택 영역 상자에 표시 됩니다. 사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> 속성을 추가 하 고 Office 응용 프로그램에 리본 메뉴가 로드 된 후 전이나 런타임에 항목을 제거 합니다.|
|**DropDown**|사용자가 선택할 수 있는 항목의 목록입니다. 사용자는 드롭다운 목록에서 새 항목을 입력할 수 없습니다.<br /><br /> 사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A> 속성 목록에 항목을 추가 합니다. 추가 하 고 런타임 시 항목을 제거할 수 있습니다.<br /><br /> 사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A> 단추 목록에 추가할 속성입니다. 그러나 추가 없으며 Office 응용 프로그램에 리본 메뉴가 로드 된 후에 런타임에 단추를 제거 합니다.|
|**EditBox**|사용자가 텍스트를 입력할 수 있는 하는 상자입니다.|
|**갤러리**|배열 또는 사용자가 선택할 수 있는 시각적 선택 항목의 표를 표시 메뉴는 합니다. 메뉴 선택 항목의 레이아웃을 제어할 수 있습니다. 사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 행과 항목을 표시 하는 열 개수 및 갤러리의 단추를 지정 하는 속성입니다.|
|**레이블**|리본 메뉴의 컨트롤을 식별 하는 데 사용할 수 있는 텍스트입니다.|
|**메뉴**|다음 컨트롤 중 하나를 포함할 수 있는 드롭다운 목록:<br /><br /> -단추<br />-확인란<br />갤러리<br />-메뉴<br />분할 단추<br />-토글 단추<br />구분 기호<br /><br /> 리본 디자이너에서 메뉴에 컨트롤을 추가 하 여 메뉴 디자인 화면을 표시 하려면 메뉴에서 아래쪽 화살표를 클릭 합니다. 리본 컨트롤을 끌어 놓을 수 있습니다 합니다 **도구 상자** 메뉴에 있습니다. 컨트롤을 정렬 하려면를 원하는 위치로 끌어 옵니다.<br /><br /> 컨트롤을 추가 하려면를 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 리본이 Office 응용 프로그램에 로드, 다음을 설정 해야 합니다 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true** 리본 메뉴가 로드 되기 전에. 이 작업을 수행 하는 방법에 대 한 정보를 참조 하세요 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.|
|**구분 기호**|가 목록의 항목을 구분 하는 데는 막대입니다. 그룹에 추가 하는 경우 막대는 세로입니다. 메뉴에 추가 될 경우 가로로 표시가 됩니다.|
|**SplitButton**|메뉴가 연결 된 단추입니다. 분할 단추는 다음 컨트롤 중 하나를 포함할 수 있습니다.<br /><br /> -단추<br />-확인란<br />갤러리<br />-메뉴<br />분할 단추<br />-토글 단추<br />구분 기호<br /><br /> 메뉴와 같이 분할 단추 자체 디자인 화면을 있습니다. 그러나 메뉴와 달리만 업데이트할 수 있습니다 분할 단추의 항목을 Office 응용 프로그램에 리본 메뉴가 로드 되기 전에 합니다. 분할 단추의 항목을 업데이트 하는 방법에 대 한 자세한 내용은 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.|
|**ToggleButton**|표시 되는 단추 누름 또는 누르지 않음.|

## <a name="HandleEventsSetProperties"></a> 이벤트 처리 및 속성 설정
 리본 디자이너를 사용 하 여 디자인 타임에 컨트롤 속성을 설정 하는 데 사용 하도록 설정 합니다 **속성** 창입니다. 또한 리본 가져오고 런타임에 리본 컨트롤의 속성을 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다.

 컨트롤의 기본 이벤트에 대 한 이벤트 처리기를 열려면 디자이너에서 컨트롤을 두 번 수 있습니다. 사용 하 여 다른 모든 컨트롤 이벤트에 대 한 이벤트 처리기를 만들 수 있습니다 합니다 **속성** 창입니다.

 리본 이벤트 및 속성에는 <xref:Microsoft.Office.Tools.Ribbon> 네임 스페이스입니다. 합니다 **리본 (비주얼 디자이너)** 항목이 자동으로 프로젝트에서이 어셈블리에 대 한 참조를 추가 하 고 적절 한 삽입 **사용 하 여** 또는 **Imports** 맨 위에 있는 문을 리본 코드 파일.

 리본 이벤트를 처리 하 고 런타임에 리본 컨트롤의 속성을 설정 하는 방법에 대 한 내용은 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.

## <a name="CustomizingMicrosoftOfficeButton"></a> Backstage 보기 사용자 지정
 리본 디자이너를 사용 하 여 컨트롤을 클릭할 때 열리는 메뉴에 추가 하는 **파일** 탭 합니다. 이 메뉴는 Backstage 보기로 불립니다 됩니다.

 리본 디자이너를 사용 하 여 기본 제공 컨트롤 전후 컨트롤을 배치할 수 없습니다. 기본 제공 컨트롤은 Backstage 뷰에 이미 표시 되는 컨트롤입니다. 기본 제공 컨트롤 전후 컨트롤을 배치 하려는 경우 리본 XML을 사용 해야 합니다. 에 대 한 자세한 내용은 **리본 (XML)** 를 참조 하십시오 [리본 XML](../vsto/ribbon-xml.md)합니다. Backstage 보기 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [개발자를 위한 Office 2010 Backstage 보기 소개](http://go.microsoft.com/fwlink/?LinkId=182189) 하 고 [개발자를 위한 Office 2010 Backstage 보기를 사용자 지정할](http://go.microsoft.com/fwlink/?LinkId=182188)합니다.

 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]

 Backstage 보기에 컨트롤을 추가 하는 방법에 대 한 정보를 참조 하세요. [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)합니다.

## <a name="Accessibility"></a> 리본 디자이너의 내게 필요한 옵션
 리본 디자이너에서 컨트롤을 이동 하려면 바로 가기 키를 사용할 수 있습니다. 일부 바로 가기 키는 모든 컨트롤에 적용 하 고 일부 메뉴가 있는 컨트롤에만 적용 합니다.

 모든 컨트롤에 적용 되는 바로 가기 키를 다음 표에 표시 됩니다.

|작업|바로 가기 키|
|------------|-----------------------|
|목록의 이전 컨트롤 앞에 컨트롤을 이동 합니다.|**Ctrl**+**Up**<br /><br /> **Ctrl**+**Left**|
|컨트롤을 목록의 다음 컨트롤 뒤로 이동 합니다.|**Ctrl**+**Down**<br /><br /> **Ctrl**+**Right**|
|동일한 그룹의 다른 한 컨트롤에서 선택 영역을 이동 합니다. 드롭다운 패널에 대 한 드롭다운 패널의 컨트롤이 부모 컨트롤 간을 이동 합니다.|**Up**<br /><br /> **아래로**|
|모든 컨트롤을 정방향으로 반복 합니다.|**Tab**|
|모든 컨트롤을 역방향으로 반복 합니다.|**Shift**+**Tab**|
|선택한 컨트롤 또는 컨트롤 집합을 삭제 합니다.|**삭제**|
|선택한 컨트롤을 복사 합니다.|**Ctrl**+**C**|
|선택한 컨트롤을 잘라냅니다.|**Ctrl**+**X**|
|클립보드에서 컨트롤을 붙여넣습니다.|**Ctrl**+**V**|
|선택 된 **도구 상자**합니다.|**Ctrl**+**Alt**+**X**|
|부모 구성 요소를 선택 합니다.|**Esc**|

 Microsoft Office 메뉴에만 적용 되는 바로 가기 키 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>, 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> 다음 표에 나와 있습니다.

|작업|바로 가기 키|
|------------|-----------------------|
|드롭다운 패널이 열려 있고 드롭다운 패널에 선택 된 컨트롤이 있는 경우 부모 컨트롤을 선택 합니다.|**왼쪽**|
|드롭다운 패널이 열려 있고 부모 컨트롤을 선택한 경우 드롭다운 패널을 닫습니다.|**왼쪽**|
|드롭다운 패널을 엽니다.|**오른쪽**|
|드롭다운 패널이 열려 있는 경우 드롭다운 패널의 첫 번째 컨트롤을 선택 합니다.|**오른쪽**|
|드롭다운 패널을 닫습니다.|**Esc**|

## <a name="see-also"></a>참고자료

- [리본 개요](../vsto/ribbon-overview.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
