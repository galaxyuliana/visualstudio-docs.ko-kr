---
title: '방법: 리본 사용자 지정 시작'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 14c4ff1e8bf443351f835d74d44b49bbb61e0321
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640118"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>방법: 리본 사용자 지정 시작
  Microsoft Office 응용 프로그램의 리본을 사용자 지정 하려면 추가 **리본 (비주얼 디자이너)** 또는 **리본 (XML)** Office 프로젝트 항목입니다.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-ribbon-to-a-project"></a>프로젝트에 리본을 추가 하려면

1. 에 **프로젝트** 메뉴에서 클릭 **새 항목 추가**합니다.

2. 에 **새 항목 추가** 대화 상자에서 **리본 (비주얼 디자이너)** 하거나 **리본 (XML)** 합니다. 이러한 템플릿에 대 한 자세한 내용은 참조 하세요. [리본 개요](../vsto/ribbon-overview.md)합니다.

3. 에 **이름을** 리본 항목에 대 한 이름을 입력 합니다.

    이름은 다음 문자를 포함할 수 없습니다.

   -   파운드(#)

   -   백분율(%)

   -   앰퍼샌드 (&)

   -   별표(*)

   -   세로 막대(|)

   -   백슬래시(\\)

   -   콜론(:)

   -   큰따옴표(")

   -   보다 작은 (\<)

   -   보다 큼(>)

   -   물음표(?)

   -   슬래시(/)

   -   선행 또는 후행 공백(' ')

   -   ("Nul", "aux", "con", "com1", "lpt1" 등)와 같은 Windows 또는 DOS에 예약 된 이름

4. **확인**을 클릭합니다.

   에 리본 항목을 표시할지 **솔루션 탐색기**합니다. 다음 단계에 대 한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)합니다.

## <a name="see-also"></a>참고자료
- [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)
- [리본 디자이너](../vsto/ribbon-designer.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
