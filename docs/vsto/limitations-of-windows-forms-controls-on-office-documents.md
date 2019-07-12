---
title: Office 문서의 Windows Forms 컨트롤의 제한 사항
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], ActiveX legacy
- ActiveX controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], limitations
- controls [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], unsupported properties and methods
- Toolbox [Office development in Visual Studio], unsupported controls
- user controls [Office development in Visual Studio], grouping controls
- Windows Forms controls [Office development in Visual Studio], Toolbox
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d5cb4bf5788e1d30933a807e2e97e064118fc076
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67823403"
---
# <a name="limitations-of-windows-forms-controls-on-office-documents"></a>Office 문서의 Windows Forms 컨트롤의 제한 사항

가지 Microsoft Office Word 문서 또는 Microsoft Office Excel 워크시트에 추가 되는 Windows Forms 컨트롤 및 Windows Forms에 추가 되는 Windows Forms 컨트롤 간의 일부 차이점이 있습니다. 추가한 경우에 예를 들어를 <xref:Microsoft.Office.Tools.Word.Controls.Button> 등의 속성을 문서에 컨트롤 <xref:System.Windows.Forms.Control.Dock>를 <xref:System.Windows.Forms.Control.Anchor>, 및 <xref:System.Windows.Forms.Control.TabIndex> 예상한 대로 작동 하지 않습니다.

이러한 차이점 중 상당수는 인해 방식으로 컨트롤을 호스팅하는 Windows Forms에 문서. Windows Forms 컨트롤을 문서에 추가 되 면는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 다음 문서의 Windows Forms 컨트롤을 호스팅하는 ActiveX 컨트롤을 포함 합니다. Windows Forms 컨트롤을 문서에 직접 포함 되지 않습니다.

[!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="limitations-of-methods-and-properties-of-windows-forms-controls"></a>Windows Forms 컨트롤의 메서드 및 속성의 제한 사항

작동 하지 않는 동일한 방식으로 문서에 Windows Form에 것이 고 따라서 것이 좋습니다는 사용 하지 않도록 Windows Forms 컨트롤의 속성과 메서드가 많이 있습니다. 예를 들어 같은 속성을 설정 <xref:System.Windows.Forms.Control.Dock> 고 <xref:System.Windows.Forms.Control.Anchor> 문서 보다는 컨테이너 ActiveX 컨트롤에 대 한 컨트롤의 위치에만 영향을 줍니다. 다음은 Word 및 Excel에 대 한 Windows Forms 컨트롤의 지원 되지 않는 메서드 및 속성의 목록입니다.

- Excel 컨트롤의 지원 되지 않는 속성:

  - <xref:System.Windows.Forms.Control.Anchor>
  - <xref:System.Windows.Forms.Control.Dock>
  - <xref:System.Windows.Forms.Control.Location>
  - <xref:System.Windows.Forms.Control.TabIndex>
  - <xref:System.Windows.Forms.Control.TabStop>
  - <xref:System.Windows.Forms.Control.TopLevelControl>

- 지원 되지 않는 메서드 및 Word 컨트롤의 속성:

  - <xref:System.Windows.Forms.Control.Hide%2A>
  - <xref:System.Windows.Forms.Control.Show%2A>
  - <xref:System.Windows.Forms.Control.Anchor>
  - <xref:System.Windows.Forms.Control.Dock>
  - <xref:System.Windows.Forms.Control.Location>
  - <xref:System.Windows.Forms.Control.TabIndex>
  - <xref:System.Windows.Forms.Control.TabStop>
  - <xref:System.Windows.Forms.Control.TopLevelControl>
  - <xref:System.Windows.Forms.Control.Visible>

또한 설정할 수 없습니다는 <xref:System.Windows.Forms.Control.Left> 또는 <xref:System.Windows.Forms.Control.Top> Word 문서에서 텍스트 줄 수 있는 Windows Forms 컨트롤의 속성입니다. Windows Forms 컨트롤은 다음 경우에는 텍스트에 맞춰 추가 됩니다.

- 프로그래밍 방식으로 Word 문서에 컨트롤을 추가 하 고 위치에 대 한 범위를 지정 하는 메서드를 사용 합니다.

- 디자인 타임에 Word 문서에 Windows Forms 컨트롤을 추가 합니다. 디자이너에서 컨트롤을 수정 하 여이 변경할 수 있습니다.

## <a name="differences-in-windows-forms-controls-on-office-documents"></a>Office 문서의 Windows Forms 컨트롤의 차이점

Windows Forms 컨트롤 일반적으로 동일 하 게 동작에서 Office 문서에 Windows Form에 수행 하지만 몇 가지 차이점이 분명히 존재 합니다. 다음 표에서 Office 문서의 Windows Forms 컨트롤에 대 한 존재 하는 차이점을 설명 합니다.

|기능|차이|
|-------------------|----------------|
|컨트롤 탭 순서|Excel 워크시트 또는 Word 문서에 배치 하는 컨트롤을 통해 탭 수 없습니다.|
|컨트롤 그룹화|사용할 수 없습니다는 <xref:System.Windows.Forms.GroupBox> Office 문서에 있는 다른 컨트롤을 포함 하는 컨트롤입니다. 문서에 직접 여러 라디오 단추를 추가 하면 라디오 단추 상호 배타적인있지 않습니다. 라디오 단추를 함께 사용할 수 없습니다; 확인 코드를 작성할 수 있습니다. 그러나, 사용자 정의 컨트롤 라디오 단추를 추가 하 고 다음 문서에 사용자 정의 컨트롤을 추가 하는 가장 좋은 방법이입니다. 자세한 내용은 Word 컨트롤 샘플 또는 Excel 컨트롤 샘플을 참조 하세요. [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)합니다.|
|컨트롤 종류|문서에 사용 되는 Windows Forms 컨트롤에서 제공 하는 클래스에 래핑됩니다는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Excel 워크시트 또는 Word 문서에 컨트롤 관련 된 추가 기능 제공. 예를 들어 있는 경우는 **단추** Excel 워크시트에서 컨트롤을 형식으로 지정 해야 <xref:Microsoft.Office.Tools.Excel.Controls.Button> 대신 <xref:System.Windows.Forms.Button> 참조 또는 개체를 캐스팅 하는 경우.|
|컨트롤 위치 및 크기|컨트롤의 위치와 크기는 ActiveX 컨트롤 컨테이너의 일부인 속성으로 결정 됩니다. ActiveX 컨트롤 속성에는 Windows Forms 컨트롤의 해당 하는 속성 값은 다른 수행 합니다. 설정 하는 경우는 `Top`, `Left`, `Height`, 또는 `Width` 컨트롤의 속성을로 측정 됩니다 픽셀 대신 가리킵니다.|
|Word 문서에서 컨트롤 위치|흐름 기반 레이아웃 컨트롤을 추가 하는 경우 컨트롤은 콘텐츠가 변경 내용으로 이동 하는 염두에 둡니다. 끌 때 단락으로 컨트롤에 고정할 수 없습니다는 **도구 상자** 텍스트에 맞춰 Word 문서에 컨트롤 추가 되기 때문에 있습니다. 다른 메서드를 사용 하 여 컨트롤을 두 번 클릭 하면 같은 컨트롤을 추가할 컨트롤 그림 삽입을 위해 설정한 Word 옵션에 따라 삽입 됩니다.<br /><br /> 설정할 수 없습니다는 `Left` 또는 `Top` 텍스트와 인라인으로 있는 컨트롤의 속성입니다.<br /><br /> 머리글 또는 바닥글에 나 하위 문서에는 컨트롤을 배치할 수 없습니다.|
|컨트롤 이벤트|컨트롤을 선택 하면 다음 순서 대로 이벤트를 발생 시킵니다.<br /><br /> 1.  `Enter`<br />2.  `GotFocus`<br /><br /> 컨트롤의 선택이 취소 되 면 다음 순서 대로 이벤트를 발생 시킵니다.<br /><br /> 1.  `Leave`<br />2.  `Validating`<br />3.  `Validated`<br />4.  `LostFocus`|
|컨트롤 크기 조정|문서 확대/축소 설정을 100% 이외의 값으로 변경한 경우 제어 하지 않는 경우에 표시 되어도 문서를 사용 하 여 확장 합니다. 예를 들어, 문서 130% 확대/축소 된 단추를 클릭 하면 메시지가 표시 됩니다 확대/축소 100%로 설정 될 때까지 컨트롤이 비활성화 되었습니다. 컨트롤을 100% 확대/축소를 변경 하는 경우 제대로 작동 합니다.|
|컨트롤 속성 값|Windows Form에 컨트롤의 속성은 정수 값으로 설정 되어, 단일 컨트롤을 Word 문서에 대 한 설정 됩니다. Excel에서 컨트롤의 속성 값을 double로 설정 됩니다. 경우는 `Height` 고 `Width` 워크시트 또는 화면 크기를 초과 하는 워크시트에 컨트롤의 속성, 값이 잘립니다.|
|컨트롤 크기 조정|새 컨트롤 차원에서 반영 되지 않습니다 여덟 개의 크기 조정 핸들 중 하나를 사용 하 여 문서에 컨트롤의 크기를 조정 하는 **속성** 창 컨트롤은 다시 선택 될 때까지 합니다.|
|동작 제어|Excel 워크시트에서 컨트롤은 워크시트 창 분할 될 때 예기치 않게 동작할 수 있습니다. 예를 들어,에 대 한 액세스는 <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> 워크시트에 에서만 사용할 수 있습니다 windows 중 하나에 있습니다.|
|컨트롤 이름 지정|컨트롤의 이름에 예약어를 사용할 수 없습니다. 예를 들어, 추가 하는 경우는 <xref:Microsoft.Office.Tools.Excel.Controls.Button> 워크시트에로 이름을 변경 하 고 **시스템**, 프로젝트를 빌드할 때 오류가 발생 합니다.|
|프로그래밍 방식으로 컨트롤 추가|런타임에 문서에 컨트롤을 추가 하려면 컨트롤의 생성자를 사용 하지 마세요. 제공 하는 도우미 메서드를 대신 사용 합니다 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 예를 들어, 사용 된 <xref:Microsoft.Office.Tools.Excel.ControlExtensions.AddButton%2A> 워크시트에 단추를 추가 하는 방법입니다. 이러한 도우미 메서드에서 지원 되지 않는 컨트롤을 추가 하려는 경우 사용할 수 있습니다는 `AddControl` 메서드. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.|
|컨트롤 복사|Windows Forms 컨트롤을 복사 하 고 런타임에 문서에 붙여넣을 경우 빈 ActiveX 컨트롤 컨테이너 문서에 붙여넣습니다. Windows Forms 컨트롤을 새 위치에서 나타나지 않습니다 및 코드 숨김 원본 컨트롤을 ActiveX 컨트롤 컨테이너에 복사 되지 않습니다.|

## <a name="limitations-in-document-level-projects"></a>문서 수준 프로젝트의 제한 사항

문서의 Windows Forms 컨트롤을 사용 하 여 몇 가지 제한 사항이 문서 수준 프로젝트에 고유 합니다.

### <a name="control-support-at-design-time"></a>디자인 타임에 컨트롤 지원

특정 Windows Forms 컨트롤에서 제거 되는 **도구 상자** Excel 워크시트 또는 Word 문서는 Visual Studio 디자이너에에서 열려 있는 경우. 기술적 제한 사항을 위반 때문에이 작업이 없거나 기능은 이미 Word 또는 Excel 내에서 사용할 수 있습니다. Excel 및 Word 프로젝트를 지 원하는 모든 Windows Forms 컨트롤 및에 표시 되는 다른 구성 요소를 **도구 상자** 문서에 포커스를 시점과 워크시트 또는 문서에서 타사 컨트롤을 추가할 수도 있습니다.

> [!NOTE]
> 모든 컨트롤에서 제거 되는 **도구 상자** 문서를 보호 하는 경우. 문서 보호에 대 한 정보를 참조 하세요 [문서 보호 문서 수준 솔루션의](../vsto/document-protection-in-document-level-solutions.md)합니다.

> [!NOTE]
> 타사 컨트롤에 있어야 합니다 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성이로 설정 **true** Office 솔루션에서 사용할 수 있습니다.

다음 컨트롤 및 구성 요소에서 사용할 수 없는 합니다 **도구 상자**:

- <xref:System.Windows.Forms.BindingNavigator>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.DataGrid>

- <xref:System.DirectoryServices.DirectoryEntry>

- <xref:System.DirectoryServices.DirectorySearcher>

- <xref:System.Windows.Forms.ErrorProvider>

- <xref:System.Diagnostics.EventLog>

- <xref:System.IO.FileSystemWatcher>

- <xref:System.Windows.Forms.FlowLayoutPanel>

- <xref:System.Windows.Forms.GroupBox>

- <xref:System.Windows.Forms.MainMenu>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Messaging.MessageQueue>

- <xref:System.Windows.Forms.NotifyIcon>

- <xref:System.Windows.Forms.PageSetupDialog>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Diagnostics.PerformanceCounter>

- <xref:System.Windows.Forms.PrintDialog>

- <xref:System.Drawing.Printing.PrintDocument>

- <xref:System.Windows.Forms.PrintPreviewControl>

- <xref:System.Diagnostics.Process>

- <xref:System.Windows.Forms.RichTextBox>

- <xref:System.IO.Ports.SerialPort>

- <xref:System.ServiceProcess.ServiceController>

- <xref:System.Windows.Forms.SplitContainer>

- <xref:System.Windows.Forms.Splitter>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TableLayoutPanel>

- <xref:System.Timers.Timer>

- <xref:System.Windows.Forms.Timer>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.ToolStripContainer>

- <xref:System.Windows.Forms.ToolStripDropDown>

- <xref:System.Windows.Forms.ToolStripDropDownMenu>

- <xref:System.Windows.Forms.ToolStripPanel>

### <a name="support-for-legacy-activex-controls"></a>레거시 ActiveX 컨트롤에 대 한 지원

ActiveX 컨트롤의 기능 손실; 되지 기존 Word 문서 또는 ActiveX 컨트롤이 포함 된 Excel 통합 문서를 사용 하는 문서 수준 Office 프로젝트를 만드는 경우 그러나 Visual Studio 내에서 문서를 새 ActiveX 컨트롤을 추가 하는 것에 대 한 지원은 없습니다. 예를 들어 Word 문서에서 단추에는 **제어** 도구 상자에 Visual Basic for Applications (VBA) 매크로 실행 하는 매크로 문서 Office 프로젝트에서 사용 된 후 실행 계속 합니다. 그러나 ActiveX 컨트롤 및 VBA 매크로 제거 하 고 Windows Forms 컨트롤을 사용 하 여 대체 하는 관리 코드 것이 좋습니다.

## <a name="see-also"></a>참고자료

- [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)
- [Windows Forms 컨트롤에 대 한 Office 문서 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)
