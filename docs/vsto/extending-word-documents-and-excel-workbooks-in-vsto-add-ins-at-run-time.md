---
title: Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- GetVstoObject method
- application-level add-ins [Office development in Visual Studio], adding controls to documents
- host items [Office development in Visual Studio], creating at run time in add-ins
- application-level add-ins [Office development in Visual Studio], extending Word documents
- application-level add-ins [Office development in Visual Studio], extending Excel workbooks
- controls [Office development in Visual Studio], adding at run time
- HasVstoObject method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2058029bfc188cd3284768e3d1782f7cda96c5c1
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402100"
---
# <a name="extend-word-documents-and-excel-workbooks-in-vsto-add-ins-at-runtime"></a>Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장
  VSTO 추가 기능을 사용하여 다음과 같은 방법으로 Word 문서 및 Excel 통합 문서를 사용자 지정할 수 있습니다.

- 열려 있는 문서 또는 워크시트에 관리되는 컨트롤을 추가합니다.

- Excel 워크시트의 기존 목록 개체를 이벤트를 표시하고 Windows Forms 데이터 바인딩 모델을 사용하여 데이터에 바인딩될 수 있는 확장된 <xref:Microsoft.Office.Tools.Excel.ListObject> 로 변환합니다.

- 특정 문서, 통합 문서 및 워크시트에 대해 Word 및 Excel에서 표시하는 애플리케이션 수준 이벤트에 액세스합니다.

  이 기능을 사용 하려면 런타임에 문서 또는 통합 문서를 확장 하는 개체를 생성 합니다.

  **적용 대상:** 이 문서의 정보는 다음 응용 프로그램에서 VSTO 추가 기능 프로젝트에 적용 됩니다. Excel 및 Word입니다. 자세한 내용은 [Office 응용 프로그램 및 프로젝트 형식으로 사용할 수 있는 기능](../vsto/features-available-by-office-application-and-project-type.md)합니다.

## <a name="generate-extended-objects-in-vsto-add-ins"></a>VSTO 추가 기능에서 확장된 개체를 생성 합니다.
 *확장 개체* 는 Visual Studio Tools for Office 런타임에서 제공하는 형식의 인스턴스로, 기본적으로 Word 또는 Excel 개체 모델에 있는 개체( *네이티브 Office 개체*라고 함)에 기능을 추가합니다. Word 또는 Excel 개체에 대한 확장 개체를 생성하려면 `GetVstoObject` 메서드를 사용합니다. 처음으로 호출 하는 `GetVstoObject` 메서드는 지정 된 Word 또는 Excel 개체 지정된 된 개체를 확장 하는 새 개체를 반환 합니다. 메서드를 호출하고 동일한 Word 또는 Excel 개체를 지정할 때마다 동일한 확장 개체가 반환됩니다.

 확장 개체의 형식은 네이티브 Office 개체의 형식과 동일한 이름을 사용하지만 형식은 <xref:Microsoft.Office.Tools.Excel> 또는 <xref:Microsoft.Office.Tools.Word> 네임스페이스에 정의되어 있습니다. 예를 들어 `GetVstoObject` 메서드를 호출하여 <xref:Microsoft.Office.Interop.Word.Document> 개체를 확장하는 경우 메서드는 <xref:Microsoft.Office.Tools.Word.Document> 개체를 반환합니다.

 `GetVstoObject` 메서드는 기본적으로 VSTO 추가 기능 프로젝트에서 사용하도록 되어 있습니다. 문서 수준 프로젝트에서 이러한 메서드를 사용할 수도 있지만 다르게 동작하며 더 적게 사용됩니다.

 확장 개체가 특정 네이티브 Office 개체에 대해 이미 생성되었는지 확인하려면 `HasVstoObject` 메서드를 사용합니다. 자세한 내용은 [Office 개체가 확장 되었는지 여부를 결정](#HasVstoObject)합니다.

### <a name="generate-host-items"></a>호스트 항목 생성
 사용 하는 경우는 `GetVstoObject` 문서 수준 개체를 확장 하 (즉,는 <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, 또는 <xref:Microsoft.Office.Interop.Word.Document>), 반환된 된 개체 라고는 *호스트 항목*합니다. 호스트 항목은 다른 확장 개체 및 컨트롤을 비롯하여 다른 개체를 포함할 수 있는 형식입니다. 이 형식은 Word 또는 Excel 주 interop 어셈블리의 해당 형식과 유사하지만 추가 기능을 제공합니다. 호스트 항목에 대 한 자세한 내용은 참조 하세요. [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)합니다.

 호스트 항목을 생성한 후에는 문서, 통합 문서 또는 워크시트에 관리되는 컨트롤을 추가하는 데 사용할 수 있습니다. 자세한 내용은 [문서 및 워크시트에 컨트롤을 관리 되는 추가](#AddControls)합니다.

#### <a name="to-generate-a-host-item-for-a-word-document"></a>Word 문서에 대한 호스트 항목을 생성하려면

- 다음 코드 예제에서는 활성 문서에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.

     [!code-vb[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#8)]
     [!code-csharp[Trin_WordAddInDynamicControls#8](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#8)]

#### <a name="to-generate-a-host-item-for-an-excel-workbook"></a>Excel 통합 문서에 대한 호스트 항목을 생성하려면

- 다음 코드 예제에서는 활성 통합 문서에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.

     [!code-vb[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#2)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#2)]

#### <a name="to-generate-a-host-item-for-an-excel-worksheet"></a>Excel 워크시트에 대한 호스트 항목을 생성하려면

- 다음 코드 예제에서는 프로젝트의 활성 워크시트에 대한 호스트 항목을 생성하는 방법을 보여 줍니다.

     [!code-vb[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#1)]

### <a name="generate-listobject-host-controls"></a>ListObject 호스트 컨트롤 생성
 `GetVstoObject` 메서드를 사용하여 <xref:Microsoft.Office.Interop.Excel.ListObject>를 확장하는 경우 메서드는 <xref:Microsoft.Office.Tools.Excel.ListObject>를 반환합니다. 합니다 <xref:Microsoft.Office.Tools.Excel.ListObject> 원래 기능의 모든 <xref:Microsoft.Office.Interop.Excel.ListObject>합니다. 또한 추가 기능이 하 고 Windows Forms 데이터 바인딩 모델을 사용 하 여 데이터에 바인딩될 수 있습니다. 자세한 내용은 [ListObject 컨트롤](../vsto/listobject-control.md)합니다.

#### <a name="to-generate-a-host-control-for-a-listobject"></a>ListObject에 대한 호스트 컨트롤을 생성하려면

- 다음 코드 예제에서는 프로젝트의 활성 워크시트에서 첫 번째 <xref:Microsoft.Office.Tools.Excel.ListObject> 에 대해 <xref:Microsoft.Office.Interop.Excel.ListObject> 를 생성하는 방법을 보여 줍니다.

     [!code-vb[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_exceladdindynamiccontrols4/ThisAddIn.vb#3)]
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../vsto/codesnippet/CSharp/trin_exceladdindynamiccontrols4/ThisAddIn.cs#3)]

### <a name="AddControls"></a> 문서 및 워크시트에 관리 되는 컨트롤 추가
 <xref:Microsoft.Office.Tools.Word.Document> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet>를 생성한 후 이러한 확장 개체가 나타내는 문서 또는 워크시트에 컨트롤을 추가할 수 있습니다. 컨트롤을 추가 하려면 사용 하 여는 `Controls` 의 속성을 <xref:Microsoft.Office.Tools.Word.Document> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet>합니다. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.

 Windows Forms 컨트롤 또는 *호스트 컨트롤*을 추가할 수 있습니다. 호스트 컨트롤은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 에서 제공하는 컨트롤로, Word 또는 Excel 주 interop 어셈블리에서 해당 컨트롤을 래핑합니다. 호스트 컨트롤에는 모든 기본 네이티브 Office 개체의 동작을 노출합니다. 또한 이벤트를 발생 하 고 Windows Forms 데이터 바인딩 모델을 사용 하 여 데이터에 바인딩될 수 있습니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)합니다.

> [!NOTE]
> VSTO 추가 기능을 사용하여 워크시트에 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤을 추가하거나 문서에 <xref:Microsoft.Office.Tools.Word.XMLNode> 또는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤을 추가할 수는 없습니다. 이러한 호스트 컨트롤은 프로그래밍 방식으로 추가할 수 없습니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)합니다.

### <a name="persist-and-remove-controls"></a>유지 및 컨트롤 제거
 문서 또는 워크시트에 관리되는 컨트롤을 추가하는 경우 문서를 저장한 후 닫으면 컨트롤이 유지되지 않습니다. 호스트 컨트롤은 모두 제거되고 기본 네이티브 Office 개체만 남겨집니다. 예를 들어 <xref:Microsoft.Office.Tools.Excel.ListObject> 가 <xref:Microsoft.Office.Interop.Excel.ListObject>가 됩니다. Windows Forms 컨트롤도 모두 제거되지만 컨트롤의 ActiveX 래퍼는 문서에 남겨집니다. 컨트롤을 정리하거나 다음에 문서를 열 때 컨트롤을 다시 만들려면 VSTO 추가 기능에 코드를 포함해야 합니다. 자세한 내용은 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)합니다.

## <a name="access-application-level-events-on-documents-and-workbooks"></a>문서 및 통합 문서에 대 한 액세스 응용 프로그램 수준 이벤트
 네이티브 Word 및 Excel 개체 모델에서 일부 문서, 통합 문서 및 워크시트 이벤트는 애플리케이션 수준에서만 발생합니다. 예를 들어 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트는 Word에서 문서를 열 때 발생하지만 이 이벤트는 <xref:Microsoft.Office.Interop.Word.Application> 클래스가 아닌 <xref:Microsoft.Office.Interop.Word.Document> 클래스에 정의되어 있습니다.

 VSTO 추가 기능에서 네이티브 Office 개체만 사용하는 경우 이러한 애플리케이션 수준 이벤트를 처리한 다음 추가 코드를 작성하여 이벤트가 발생한 문서가 사용자 지정한 문서인지를 확인해야 합니다. 호스트 항목은 이러한 이벤트를 문서 수준에서 제공하므로 특정 문서에 대한 이벤트를 더 쉽게 처리할 수 있습니다. 호스트 항목을 생성한 다음 해당 호스트 항목에 대한 이벤트를 처리 할 수 있습니다.

### <a name="example-that-uses-native-word-objects"></a>네이티브 Word 개체를 사용 하는 예제
 다음 코드 예제에서는 Word 문서에 대한 애플리케이션 수준 이벤트를 처리하는 방법을 보여 줍니다. `CreateDocument` 메서드는 새 문서를 만든 다음 이 문서가 저장되지 않도록 하는 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트 처리기를 정의합니다. 이벤트에 대해 발생 하는 응용 프로그램 수준 이벤트는를 <xref:Microsoft.Office.Interop.Word.Application> 개체 및 이벤트 처리기를 비교 해야 합니다는 `Doc` 매개 변수를 `document1` 여부를 확인 하는 개체 `document1` 저장된 된 문서를 나타냅니다.

 [!code-vb[Trin_WordAddInDynamicControls #12](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#12)]
 [!code-csharp[Trin_WordAddInDynamicControls#12](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#12)]

### <a name="examples-that-use-a-host-item"></a>호스트 항목을 사용 하는 예제
 다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document> 이벤트를 처리하여 이 프로세스를 간소화합니다. `CreateDocument2` 이러한 예제에서 메서드 생성를 <xref:Microsoft.Office.Tools.Word.Document> 확장 하는 합니다 `document2` 개체, 한 다음 정의 <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> 문서 저장 되는 것을 방지 하는 이벤트 처리기입니다. 이벤트 처리기가 경우에만 호출 `document2` 저장 되 고 저장을 취소할 수 저장 된 문서를 확인 하는 추가 작업을 수행 하지 않고 작업 합니다.

 다음 코드 예제에서는 이 작업을 보여 줍니다.

 [!code-vb[Trin_WordAddInDynamicControls #13](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#13)]
 [!code-csharp[Trin_WordAddInDynamicControls#13](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#13)]

## <a name="HasVstoObject"></a> Office 개체가 확장 되었는지 여부를 결정 합니다.
 확장 개체가 특정 네이티브 Office 개체에 대해 이미 생성되었는지 확인하려면 `HasVstoObject` 메서드를 사용합니다. 이 메서드는 반환 **true** 확장된 개체가 이미 생성 된 경우.

 `Globals.Factory.HasVstoMethod` 메서드를 사용하세요. 확장 개체에 대해 테스트하려는 네이티브 Word 또는 Excel 개체(예: <xref:Microsoft.Office.Interop.Word.Document> 또는 <xref:Microsoft.Office.Interop.Excel.Worksheet>)를 전달합니다.

 `HasVstoObject` 메서드는 지정된 Office 개체에 확장 개체가 있는 경우에만 코드를 실행하려는 경우 유용합니다. 예를 들어 Word VSTO 추가 기능을 처리 하는 경우는 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 저장 되기 전에 문서를 관리 되는 컨트롤을 제거 하려면 사용 하 여 이벤트를 `HasVstoObject` 문서가 확장 되었는지 여부를 결정 하는 방법입니다. 문서 확장 되지 않은 경우 해당 컨트롤 관리 없습니다 및 이벤트 처리기는 문서에 컨트롤을 정리 하려고 하지 않고도 반환할 수 있습니다.

## <a name="see-also"></a>참고자료
- [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)
- [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)
