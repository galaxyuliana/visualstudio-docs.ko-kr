---
title: '방법: 프로그래밍 방식으로 문서 저장'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 965f8d9661d30d23365fe324f7102e15fafec77c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056278"
---
# <a name="how-to-programmatically-save-documents"></a>방법: 프로그래밍 방식으로 문서 저장
  Microsoft Office Word 문서를 저장 하는 방법은 여러 가지가 있습니다. 문서의 이름을 변경 하지 않고 문서를 저장할 수 있습니다 하거나 새 이름으로 문서를 저장할 수 있습니다.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="save-a-document-without-changing-the-name"></a>이름을 변경 하지 않고 문서를 저장 합니다.

### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>문서 수준 사용자 지정을 사용 하 여 연결 된 문서를 저장 하려면

1. <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 메서드를 호출합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]

### <a name="to-save-the-active-document"></a>활성 문서를 저장 하려면

1. 호출 된 <xref:Microsoft.Office.Interop.Word._Document.Save%2A> 활성 문서에 대 한 메서드. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

    [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
    [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]

   저장 하려는 문서 활성 문서 인지 확실 하지 않은 경우 해당 이름으로를 참조할 수 있습니다.

### <a name="to-save-a-document-specified-by-name"></a>이름별로 지정 된 문서를 저장 하려면

1. 문서 이름을 인수로 사용 된 <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션입니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]

## <a name="save-a-document-with-a-new-name"></a>새 이름으로 문서를 저장 합니다.
 새 이름으로 문서를 저장 하려면 SaveAs 메서드를 사용 합니다. 이 방법을 사용할 수는 <xref:Microsoft.Office.Tools.Word.Document> 네이티브 또는 문서 수준 Word 프로젝트에서 호스트 항목 <xref:Microsoft.Office.Interop.Word.Document> Word 프로젝트에는 개체입니다. 이 메서드는 새 파일 이름을 지정 했지만 다른 인수는 선택 사항 필요 합니다.

> [!NOTE]
>  표시 하는 경우는 **SaveAs** 대화 상자 내에 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트 처리기 `ThisDocument` 설정를 *취소* 매개 변수를 **false**, 응용 프로그램 수 예기치 않게 종료. 설정 하는 경우는 *취소할* 매개 변수를 **true**, 자동 저장에 사용할 수 없음을 나타내는 오류 메시지가 나타납니다.

### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>새 이름으로 문서 수준 사용자 지정을 사용 하 여 연결 된 문서를 저장 하려면

1. 호출 된 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드는 `ThisDocument` 정규화 된 경로 파일 이름을 사용 하 여 프로젝트에서 클래스. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다. 이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.

    > [!NOTE]
    >  <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 대상 디렉터리가 없는 경우 또는 파일을 저장할 다른 문제가 있는 경우 메서드에서 예외가 throw 됩니다. 사용 하는 것이 좋습니다를 **try... catch** 주위 차단는 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드 또는 메서드 내에서 호출 합니다.

     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]

### <a name="to-save-a-native-document-with-a-new-name"></a>새 이름으로 기본 문서를 저장 하려면

1. 호출 된 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드는 <xref:Microsoft.Office.Interop.Word.Document> 정규화 된 경로 파일 이름을 사용 하 여를 저장 하려는. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다.

     다음 코드 예제에서는 새 이름을 사용 하 여 활성 문서를 저장합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.

    > [!NOTE]
    >  <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 대상 디렉터리가 없는 경우 또는 파일을 저장할 다른 문제가 있는 경우 메서드에서 예외가 throw 됩니다. 사용 하는 것이 좋습니다를 **try... catch** 주위 차단는 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드 또는 메서드 내에서 호출 합니다.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]

## <a name="compile-the-code"></a>코드 컴파일
 이 코드 예제에는 다음이 필요합니다.

- 라는 이름으로 문서를 저장 하려면 *NewDocument.doc* 라는 디렉터리에 있어야 *테스트* 에서 C 드라이브입니다.

- 라는 디렉터리를 새 이름으로 문서를 저장 하려면 *테스트* C 드라이브에 있어야 합니다

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)
- [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)
- [문서 호스트 항목](../vsto/document-host-item.md)
- [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)
