---
title: '방법: 리본 메뉴에 개발 도구 탭 표시'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2e1855c64e88cdf45715654eede780aaa20d0258
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60091423"
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>방법: 리본 메뉴에 개발 도구 탭 표시
  액세스 하는 **개발자** 탭 Office 응용 프로그램의 리본에서 기본적으로 표시 되지 않으므로 해당 탭을 표시 하도록 구성 해야 있습니다. 예를 표시 Word의 문서 수준 사용자 지정에 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 추가하려면 해당 탭을 표시해야 합니다.

> [!NOTE]
>  이 지침은 Office 2010 또는 이상의 응용 프로그램에만 적용됩니다. 2007 Microsoft Office System에이 탭을 표시 하려는 경우이 항목의 다음 버전을 참조 [방법: 리본 메뉴에 개발 도구 탭 표시](https://web.archive.org/web/20140303033431/msdn.microsoft.com/library/bb608625(v=vs.90).aspx
)합니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

> [!NOTE]
>  액세스 없는 **개발자** 탭 합니다.

## <a name="to-show-the-developer-tab"></a>개발자 탭을 표시하려면

1. 이 항목에서 지원하는 Office 응용 프로그램을 시작합니다. 참조를 **적용 대상:** 이 항목의 앞 부분에서.

2. 에 **파일** 탭을 선택 합니다 **옵션** 단추입니다.

     다음 그림에서는 합니다 **파일** 탭 및 **옵션** Office 2010의 단추입니다.

     ![Outlook 2010의 옵션 파일 선택](../vsto/media/vsto-office-file-tab.png "Outlook 2010의 옵션 파일 선택")

     다음 그림에서는 합니다 **파일** Office 2013의 탭 합니다.

     ![Outlook 2013의 파일 탭](../vsto/media/vsto-office2013-filetab.png "Outlook 2013의 파일 탭")

     다음 그림에서는 합니다 **옵션** Office 2013의 단추입니다.

     ![Outlook 2013 Preview의 옵션 단추](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 preview에서의 옵션 단추")

3. 에 _ApplicationName_**옵션** 대화 상자를 선택 합니다 **리본 사용자 지정** 단추입니다.

     다음 그림에서는 합니다 **옵션** 대화 상자와 **리본 사용자 지정** Excel 2010의 단추입니다. 이 단추의 위치는 이 항목의 위쪽 “적용 대상" 섹션에 나열된 다른 모든 응용 프로그램에서 유사합니다.

     ![사용자 지정 리본 단추](../vsto/media/vsto-office2010-customizeribbonbutton.png "리본 사용자 지정 단추")

4. 기본 탭 목록에서 선택 합니다 **개발자** 확인란 합니다.

     다음 그림에서는 합니다 **개발자** Word 2010에서 확인란 및 [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]합니다. 이 확인란의 위치는 이 항목의 위쪽 “적용 대상" 섹션에 나열된 다른 모든 응용 프로그램에서 유사합니다.

     ![Word 옵션 대화 상자에서 개발자 확인란](../vsto/media/vsto-office2010-developercheckbox.png "Word 옵션 대화 상자에서 확인란 The Developer")

5. 선택 된 **확인** 를 닫으려면 단추를 합니다 **옵션** 대화 상자.

## <a name="see-also"></a>참고자료
- [Office UI 사용자 지정](../vsto/office-ui-customization.md)
