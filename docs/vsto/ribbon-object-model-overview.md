---
title: 리본 개체 모델 개요
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], object model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5958eb6fb8fd14dd510fa87d900efa76cb6f6a87
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60040718"
---
# <a name="ribbon-object-model-overview"></a>리본 개체 모델 개요
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 가져오고 런타임에 리본 컨트롤의 속성을 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다. 예를 들어 수 동적으로 메뉴 컨트롤을 채우는 또는 표시 하거나 숨길 수 컨트롤 컨텍스트. Office 응용 프로그램에서 리본 메뉴가 로드 되기 전에만 있지만 리본, 탭, 그룹 및 컨트롤도 추가할 수 있습니다. 정보를 참조 하세요 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

 이 리본 개체 모델은 주로 구성 합니다 [리본 클래스](#RibbonClass), [리본 이벤트](#RibbonEvents), 및 [리본 컨트롤 클래스](#RibbonControlClasses)합니다.

## <a name="RibbonClass"></a> Ribbon 클래스
 새로 추가한 경우 **리본 (비주얼 디자이너)** 추가 하는 Visual Studio 프로젝트에 항목을 **리본** 프로젝트에 클래스입니다. 합니다 **리본** 클래스에서 상속 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> 클래스입니다.

 이 클래스는 리본 코드 파일 및 리본 디자이너 코드 파일 간에 분할 되는 partial 클래스로 표시 됩니다.

## <a name="RibbonEvents"></a> 리본 이벤트
 합니다 **리본** 클래스는 다음 세 가지 이벤트를 포함 합니다.

|이벤트(event)|설명|
|-----------|-----------------|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office 응용 프로그램에 리본 사용자 지정 로드 될 때 발생 합니다. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> 이벤트 처리기는 리본 코드 파일에 자동으로 추가 됩니다. 이 이벤트 처리기를 사용 하 여 리본이 로드 될 때 사용자 지정 코드를 실행 합니다.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|하면 리본 사용자 지정의 캐시 이미지에 리본 메뉴가 로드 하는 경우. 이 이벤트 처리기에서 리본 메뉴 이미지를 캐시 하는 코드를 작성 하는 경우 성능이 약간 향상을 얻을 수 있습니다. 자세한 내용은 <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>을 참조하세요.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|리본 인스턴스가 닫힐 때 발생 합니다.|

## <a name="RibbonControlClasses"></a> 리본 컨트롤
 <xref:Microsoft.Office.Tools.Ribbon> 네임 스페이스에 표시 되는 각 컨트롤에 대 한 형식을 포함 합니다 **Office 리본 컨트롤** 그룹을 **도구 상자**.

 다음 표에서 각 종류를 보여 줍니다. `Ribbon` 제어 합니다. 각 컨트롤의 설명을 참조 하세요 [리본 개요](../vsto/ribbon-overview.md)합니다.

|컨트롤 이름|클래스 이름|
|------------------|----------------|
|**Object^**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**Button**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|
|**DropDown**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|
|**EditBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**갤러리**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**레이블**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|
|**메뉴**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**구분 기호**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|
|**SplitButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**Tab**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|

 합니다 <xref:Microsoft.Office.Tools.Ribbon> 에서 컨트롤 클래스의 이름 사용 하 여 이름 충돌을 방지 하려면 이러한 형식에 대 한 "리본" 접두사를 사용 하는 네임 스페이스는 <xref:System.Windows.Forms> 네임 스페이스입니다.

 리본 디자이너에 컨트롤을 추가할 때 리본 디자이너 리본 디자이너 코드 파일의 필드와 해당 컨트롤에 대 한 클래스를 선언 합니다.

### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>리본 컨트롤의 속성을 사용 하 여 일반적인 작업
 각 `Ribbon` 컨트롤 컨트롤에 레이블을 할당 하거나 컨트롤 숨기기 및 표시와 같은 다양 한 작업을 수행 하는 데 사용할 수 있는 속성을 포함 합니다.

 경우에 따라 속성은 리본 메뉴가 로드 또는 동적 메뉴에 컨트롤을 추가한 후 읽기 전용 됩니다. 자세한 내용은 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.

 다음 표에서 몇 가지를 사용 하 여 수행할 수 있는 작업 설명 `Ribbon` 속성을 제어 합니다.

|작업|방법|
|--------------------|--------------|
|컨트롤을 표시 하거나 숨깁니다.|Visible 속성을 사용 합니다.|
|컨트롤을 사용 하지 않도록 설정 하거나 사용 합니다.|Enabled 속성을 사용 합니다.|
|컨트롤의 크기를 설정 합니다.|ControlSize 속성을 사용 합니다.|
|컨트롤에 표시 되는 이미지를 가져옵니다.|이미지 속성을 사용 합니다.|
|컨트롤의 레이블을 변경 합니다.|Label 속성을 사용 합니다.|
|컨트롤에 사용자 정의 데이터를 추가 합니다.|태그 속성을 사용 합니다.|
|항목을 가져오고를 <xref:Microsoft.Office.Tools.Ribbon.RibbonBox>하십시오 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>, 또는<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> 컨트롤입니다.|항목 속성을 사용 합니다.|
|항목을 추가 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 제어 합니다.|항목 속성을 사용 합니다.|
|제어를 추가 하는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>합니다.|항목 속성을 사용 합니다.<br /><br /> 컨트롤을 추가 하려면를 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 리본이 Office 응용 프로그램에 로드, 다음을 설정 해야 합니다 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true** Office 응용 프로그램에 리본 메뉴가 로드 되기 전에 합니다. 정보를 참조 하세요 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.|
|선택한 항목 가져오기는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>합니다.|SelectedItem 속성을 사용 합니다. 에 대 한는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>를 사용 하 여는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> 속성입니다.|
|그룹 로그온을 <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>입니다.|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> 속성을 사용합니다.|
|행 및 열에 표시 되는 횟수를 지정 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>합니다.|사용 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 고 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 속성입니다.|

## <a name="SettingReadOnlyProperties"></a> 읽기 전용으로 설정 하는 속성 설정
 리본 메뉴가 로드 되기 전에 일부 속성 에서만 설정할 수 있습니다. 이러한 속성을 설정 하려면 다음 세 위치 가지가 있습니다.

- Visual studio에서 **속성** 창입니다.

- 생성자에는 **리본** 클래스입니다.

- 에 `CreateRibbonExtensibilityObject` 메서드를 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 프로젝트의 클래스입니다.

  동적 메뉴는 몇 가지 예외를 제공합니다. 새 컨트롤을 만들 지정, 해당 속성을 설정 및 다음 메뉴를 포함 하는 리본이 로드 된 후에 런타임에 동적 메뉴에 추가 합니다.

  언제 든 지 동적 메뉴에 추가한 컨트롤의 속성을 설정할 수 있습니다.

  자세한 내용은 [속성을 읽기 전용으로 바뀌면](#ReadOnlyProperties)합니다.

### <a name="set-properties-in-the-constructor-of-the-ribbon"></a>리본 메뉴의 생성자에서 속성을 설정 합니다.
 속성을 설정할 수는 `Ribbon` 컨트롤의 생성자에는 **리본** 클래스. 이 코드에 대 한 호출 뒤에 나타나야 합니다.는 `InitializeComponent` 메서드. 다음 예에서는 현재 17시 이면 새 단추를 그룹에 추가 태평양 표준시 (utc-8) 이상.

 다음 코드를 추가 합니다.

 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]

 시각적 개체의 C# Visual Studio 2008에서 업그레이드 하는 프로젝트에서는 생성자 리본 코드 파일에 나타납니다.

 Visual Basic 프로젝트에서 또는 시각적 개체의 C# 프로젝트에서 만든 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], 생성자 리본 디자이너 코드 파일에 나타납니다. 이 파일의 이름은 *YourRibbonItem*합니다. Designer.cs 또는 *YourRibbonItem*합니다. Designer.vb 합니다. Visual Basic 프로젝트에서이 파일을 보려면 먼저 클릭 해야 합니다 **모든 파일 표시** 솔루션 탐색기 단추.

### <a name="set-properties-in-the-createribbonextensibilityobject-method"></a>프로젝트 메서드의 속성을 설정 합니다.
 속성을 설정할 수 있습니다는 `Ribbon` 재정의 하는 경우를 제어 합니다 `CreateRibbonExtensibilityObject` 에서 메서드는 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 프로젝트의 클래스. 에 대 한 자세한 내용은 합니다 `CreateRibbonExtensibilityObject` 메서드를 참조 하세요 [리본 개요](../vsto/ribbon-overview.md)합니다.

 리본 속성을 설정 하는 다음 예제에서는 합니다 `CreateRibbonExtensibilityObject` 메서드는 `ThisWorkbook` Excel 통합 문서 프로젝트의 클래스.

 다음 코드를 추가 합니다.

 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]

### <a name="ReadOnlyProperties"></a> 읽기 전용 되는 속성
 다음 표에서 리본 메뉴가 로드 되기 전에 설정할 수 있는 속성을 보여 줍니다.

> [!NOTE]
>  언제 든 지 동적 메뉴의 컨트롤의 속성을 설정할 수 있습니다. 이 표에서 경우에 적용 되지 않습니다.

|속성|리본 컨트롤 클래스|
|--------------|--------------------------|
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**ColumnCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ControlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**Dynamic**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**Global**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**ImageName**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**MaxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**이름**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|
|**위치**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**RowCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**Tabs**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**제목**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|

### <a name="set-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Outlook 검사기에 나타나는 리본 메뉴에 대 한 속성을 설정 합니다.
 리본 메뉴의 새 인스턴스를 사용자가 리본 메뉴 표시 되는 검사기를 열 때마다 생성 됩니다. 그러나 리본 메뉴의 첫 번째 인스턴스가 만들어지기 전에 위의 표에 나열 된 속성을 설정할 수 있습니다. 첫 번째 인스턴스는을 만든 후 첫 번째 인스턴스는 Outlook에서 리본을 로드 하는 데 사용 하는 XML 파일을 정의 하기 때문에 읽기 전용으로 바뀌면 이러한 속성입니다.

 리본 메뉴의 다른 인스턴스를 만들 때 다른 값으로 이러한 속성을 설정 하는 조건부 논리를 사용 하는 경우이 코드는 효과가 없습니다.

> [!NOTE]
>  있는지 확인 합니다 **이름** Outlook 리본 메뉴에 추가한 각 컨트롤에 대 한 속성. 런타임 시 Outlook 리본 메뉴에 컨트롤을 추가 하는 경우 코드에서이 속성을 설정 해야 합니다. 디자인 타임에 Outlook 리본 메뉴에 컨트롤을 추가 하는 경우 이름 속성은 자동으로 설정 합니다.

## <a name="ribbon-control-events"></a>리본 컨트롤 이벤트
 각 컨트롤 클래스에는 하나 이상의 이벤트가 포함 됩니다. 다음 표에서 이러한 이벤트를 설명 합니다.

|이벤트(event)|설명|
|-----------|-----------------|
|클릭 대상|컨트롤을 클릭할 때 발생 합니다.|
|TextChanged|편집 상자 또는 콤보 상자의 텍스트가 변경 될 때 발생 합니다.|
|ItemsLoading|컨트롤의 항목 컬렉션은 Office가 요청 될 때 발생 합니다. 컨트롤의 속성을 변경 하는 코드 또는 호출 될 때까지 office 항목 컬렉션을 캐시 합니다 <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> 메서드.|
|ButtonClick|경우 단추를 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 를 클릭 합니다.|
|SelectionChanged|발생 경우 선택 항목을 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 변경 합니다.|
|DialogLauncherClick|그룹의 오른쪽 아래 모서리에 있는 대화 상자 표시 아이콘을 클릭할 때 발생 합니다.|

 이러한 이벤트에 대 한 이벤트 처리기는 다음 두 개의 매개 변수입니다.

|매개 변수|설명|
|---------------|-----------------|
|*sender*|<xref:System.Object> 이벤트를 발생 시킨 컨트롤을 나타내는입니다.|
|*e*|<xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs>이 들어 있는 <xref:Microsoft.Office.Core.IRibbonControl>입니다. 이 컨트롤에서 제공 하는 리본 개체 모델에서 사용할 수 없는 모든 속성에 액세스 하는 데는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다.|

## <a name="see-also"></a>참고자료
- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
- [리본 개요](../vsto/ribbon-overview.md)
- [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [연습: 런타임에 리본의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)
- [Outlook의 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)
- [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)
- [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [방법: 추가 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)
