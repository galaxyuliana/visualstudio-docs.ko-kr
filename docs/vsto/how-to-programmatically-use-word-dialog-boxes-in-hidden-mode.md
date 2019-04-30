---
title: '방법: 프로그래밍 방식으로 숨김된 모드에서 Word 대화 상자를 사용 하 여'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e7a422e9548fabefa2066fb439c01e382586cd36
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62961607"
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>방법: 프로그래밍 방식으로 숨김된 모드에서 Word 대화 상자를 사용 하 여
  사용자에 게 표시 하지 않고 Microsoft Office Word의 기본 제공 대화 상자를 호출 하 여 호출 하 여 복잡 한 작업을 수행할 수 있습니다. 사용 하 여이 수행할 수 있습니다 합니다 <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> 메서드를 <xref:Microsoft.Office.Interop.Word.Dialog> 호출 하지 않고 개체를 <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> 메서드.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="examples"></a>예제
 다음 코드 예제에 사용 하는 방법을 보여 줍니다 합니다 **페이지 설정** 사용자 입력 없이 사용 하 여 여러 페이지 설정 속성을 설정 하는 숨김된 모드에서 대화 상자. 예제에서는 사용을 <xref:Microsoft.Office.Interop.Word.Dialog> 지정 페이지 크기를 구성 하는 개체입니다. 위쪽 여백, 아래쪽 여백 등과 등 페이지 설정에 대 한 특정 설정의 런타임에 바인딩된 속성으로 사용할 수는 <xref:Microsoft.Office.Interop.Word.Dialog> 개체입니다. 이러한 속성은 동적으로 런타임 시 Word에서 생성 됩니다.

 다음 예제에는 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다. 여기서 **Option Strict** 전원이 꺼져 Visual C# 프로젝트에서 대상으로 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]합니다. 이러한 프로젝트는 Visual Basic 및 Visual C# 컴파일러에서 런타임에 바인딩 기능을 사용할 수 있습니다. 이 예제를 사용 하려면에서 실행 합니다 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.

 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]

 다음 예제에는 Visual Basic 프로젝트에서이 작업을 수행 하는 방법을 보여 줍니다. 여기서 **Option Strict** 켜져 있습니다. 이러한 프로젝트에서는 런타임에 바인딩된 속성에 액세스 하려면 리플렉션을 사용 해야 합니다. 이 예제를 사용 하려면에서 실행 합니다 `ThisDocument` 또는 `ThisAddIn` 프로젝트에서 클래스입니다.

 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]

## <a name="see-also"></a>참고자료
- [방법: 프로그래밍 방식으로 Word에서 기본 제공 대화 상자를 사용 하 여](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)
- [Word 개체 모델 개요](../vsto/word-object-model-overview.md)
- [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)
- [리플렉션(C#)](/dotnet/csharp/programming-guide/concepts/reflection)
- [리플렉션(Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)
