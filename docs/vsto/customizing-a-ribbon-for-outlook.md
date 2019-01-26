---
title: Outlook의 리본을 사용자 지정
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Inspectors [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], Ribbon
- customizing the Ribbon, about customizing the Ribbon
- custom Ribbon, about customizing the Ribbon
- Ribbon [Office development in Visual Studio], Outlook
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7e7b99272e4ef7ca59566c3de0ab9f89804d4cbd
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863632"
---
# <a name="customize-a-ribbon-for-outlook"></a>Outlook의 리본을 사용자 지정
  Microsoft Office Outlook에서 리본을 사용자 지정할 경우 응용 프로그램에서 사용자 지정 리본이 나타나는 위치를 고려해야 합니다. Outlook에서 리본은 사용자가 메일 메시지 만들기 등의 특정 작업을 수행할 때 열리는 창과 기본 응용 프로그램 UI(사용자 인터페이스)에 표시됩니다. 이러한 응용 프로그램 창의 이름을 검사기라고 합니다.  
  
 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? Outlook에서 리본을 사용자 지정 리본 디자이너 사용 ](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="add-a-custom-ribbon-to-the-main-application-ui"></a>기본 응용 프로그램 UI 사용자 지정 리본 추가  
 Outlook의 기본 응용 프로그램 UI를 탐색기라고 합니다. 사용 중인 경우는 **리본 (비주얼 디자이너)** 를 클릭 하 여 탐색기에 리본 메뉴를 추가할 수는 항목을 **RibbonType** 에서 리본 메뉴의 속성을 **속성** 창 다음을 선택 하 고 **Microsoft.Outlook.Explorer**합니다.  
  
## <a name="assign-a-ribbon-to-an-inspector"></a>검사기에 리본 할당  
 검사기에 대한 메시지 클래스에 해당하는 리본 형식을 지정하여 사용자 지정하려는 검사기를 식별합니다.  
  
 사용 중인 경우는 **리본 (비주얼 디자이너)** 항목을 클릭 합니다 **RibbonType** 에서 리본 메뉴의 속성을 **속성** 창 및 선택 하 고 하나 이상의 리본 Id 값의 목록입니다.  
  
 프로젝트에 리본을 두 개 이상 추가할 수 있습니다. 두 개 이상의 리본이 리본 ID를 공유하는 경우 프로젝트의 `ThisAddin` 클래스에서 `CreateRibbonExtensibilityObject` 메서드를 재정의하여 런타임에 표시할 리본을 지정합니다. 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)합니다. 각 리본 형식에 대 한 자세한 내용은 기술 문서를 참조 하세요 [Outlook 2007에서 리본을 사용자 지정](/previous-versions/office/developer/office-2007/bb226712(v=office.12))합니다.  
  
## <a name="specify-the-ribbon-type-by-using-ribbon-xml"></a>리본 XML을 사용 하 여 리본 형식 지정  
 사용 중인 경우는 **리본 (XML)** 항목의 값을 확인 합니다 *ribbonID* 에서 매개 변수를 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드 및 적절 한 리본을 반환 합니다.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드는 Visual Studio를 통해 리본 코드 파일에서 자동으로 생성됩니다. 합니다 *ribbonID* 매개 변수는 탐색기 또는 검사기의 특정 형식을 식별 하는 문자열입니다. 가능한 값의 전체 목록은 합니다 *ribbonID* 매개 변수를 기술 문서를 참조 하십시오 [Outlook 2007에서 리본을 사용자 지정](/previous-versions/office/developer/office-2007/bb226712(v=office.12))합니다.  
  
 다음 코드 예제에서는 `Microsoft.Outlook.Mail.Compose` 검사기에만 사용자 지정 리본을 표시하는 방법을 보여 줍니다. 사용자가 새 메일 메시지를 만들 때 열리는 검사기입니다. 표시할 리본에 지정 된 합니다 `GetResourceText()` 에서 생성 되는 메서드를 **리본** 클래스입니다. 에 대 한 자세한 내용은 합니다 **리본** 클래스를 참조 하십시오 [리본 XML](../vsto/ribbon-xml.md)합니다.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#1)]
 [!code-vb[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#1)]  
  
## <a name="see-also"></a>참고자료  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [Ribbon XML](../vsto/ribbon-xml.md)  
