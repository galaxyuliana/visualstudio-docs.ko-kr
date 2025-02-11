---
title: '방법: 바로 가기 메뉴에 명령 추가'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office menus, creating
- Office development in Visual Studio, context menus
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3b20b10a37908e2c9744aeac63bb3eda091da478
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62826407"
---
# <a name="how-to-add-commands-to-shortcut-menus"></a>방법: 바로 가기 메뉴에 명령 추가
  이 항목에는 VSTO 추가 기능을 사용 하 여 Office 응용 프로그램에서 바로 가기 메뉴에 명령을 추가 하는 방법을 보여 줍니다.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

### <a name="to-add-commands-to-shortcut-menus-in-office"></a>Office에서 바로 가기 메뉴에 명령을 추가하려면

1. **리본 XML** 항목을 문서 수준 또는 VSTO 추가 기능 프로젝트에 추가합니다. 자세한 내용은 [방법: 리본 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다. 입력

2. **솔루션 탐색기**에서 **ThisAddin.cs** 또는 **ThisAddin.vb**를 선택합니다.

3. 메뉴 모음에서 **보기** > **코드**를 차례로 선택합니다.

     **ThisAddin** 클래스 파일이 코드 편집기에서 열립니다.

4. **ThisAddin** 클래스에 다음 코드를 추가합니다. 이 코드는 `CreateRibbonExtensibilityObject` 메서드를 재정의하고 Office 애플리케이션에 리본 XML 클래스를 반환합니다.

     [!code-csharp[Trin_WordAddIn_Menus#1](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#1)]
     [!code-vb[Trin_WordAddIn_Menus#1](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#1)]

5. **솔루션 탐색기**에서 리본 XML 파일을 선택합니다. 기본적으로 리본 XML 파일 이름은 *Ribbon1.xml*합니다.

6. 메뉴 모음에서 **보기** > **코드**를 차례로 선택합니다.

     코드 편집기에서 리본 xml 파일이 열립니다.

7. 코드 편집기에서 바로 가기 메뉴와 바로 가기 메뉴에 추가할 컨트롤을 설명하는 XML을 추가합니다.

     다음 예제에서는 Word 문서의 바로 가기 메뉴에 단추, 메뉴 및 갤러리 컨트롤을 추가합니다. 이 바로 가기 메뉴의 컨트롤 ID는 ContextMenuText입니다. 전체 목록은 Office 2010 바로 가기 컨트롤 ID, 참조 [Office 2010 도움말 파일: Office fluent 사용자 인터페이스 제어 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">
      <contextMenus>
        <contextMenu idMso="ContextMenuText">
          <button id="MyButton" label="My Button" insertBeforeMso="HyperlinkInsert" onAction="GetButtonID" />
          <menu id="MySubMenu" label="My Submenu" >
            <button id="MyButton2" label="Button on submenu" />
          </menu>
          <gallery id="galleryOne" label="My Gallery">
            <item id="item1" imageMso="HappyFace" />
            <item id="item2" imageMso="HappyFace" />
            <item id="item3" imageMso="HappyFace" />
            <item id="item4" imageMso="HappyFace" />
          </gallery>
        </contextMenu>
      </contextMenus>
    </customUI>
    ```

8. **솔루션 탐색기**에서 **MyRibbon.cs** 또는 **MyRibbon.vb**를 선택합니다.

9. 콜백 메서드를 추가 합니다 `Ribbon1` 처리 하려는 각 컨트롤에 대 한 클래스입니다.

     다음 콜백 메서드는 **My Button** 단추를 처리합니다. 이 코드는 활성 문서의 현재 커서 위치에 문자열을 추가합니다.

     [!code-vb[Trin_WordAddIn_Menus#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/ribbon1.vb#2)]
     [!code-csharp[Trin_WordAddIn_Menus#2](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/ribbon1.cs#2)]

## <a name="see-also"></a>참고자료
- [Office UI 사용자 지정](../vsto/office-ui-customization.md)
- [연습: 책갈피에 대 한 바로 가기 메뉴 만들기](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)
- [Office 2010의 상황에 맞는 메뉴를 사용자 지정](http://go.microsoft.com/fwlink/?LinkId=182186)
