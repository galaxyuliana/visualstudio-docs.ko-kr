---
title: Outlook 양식 영역의 사용자 지정 작업
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], custom actions
- custom actions [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0044991b330594d80422f0c6ac1d1d64b1fec237
ms.sourcegitcommit: b7f25ae08e45fcaa84a84276b588cf6799cc7620
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57567185"
---
# <a name="custom-actions-in-outlook-form-regions"></a>Outlook 양식 영역의 사용자 지정 작업
  사용자가 Microsoft Office Outlook 항목에 응답할 수 있도록 단추를 표시 하는 작업입니다. 예를 들어, 메일 항목에 응답 하려면 사용자가 클릭 합니다 **회신**를 **전체 회신**, 또는 **앞으로** 작업 단추입니다. 이러한 각 작업을 새 메일 항목을 만들고 원래 항목의 정보를 사용 하 여 항목의 필드를 채웁니다.

 사용자 지정 작업 종류의 Outlook 항목을 만들 수 있습니다. 예를 들어 열린 새 약속 또는 작업 항목을 사용자 지정 작업을 추가할 수 있습니다. 사용자 지정 작업의 속성을 설정 또는 사용자 지정 코드를 사용 하 여 새 항목의 필드를 채웁니다. 사용자 지정 작업에 표시 된 **사용자 지정 작업** Outlook 검사기 창에 열려 있는 항목의 드롭다운 목록입니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="add-custom-actions-to-a-form-region"></a>양식 영역에 사용자 지정 작업 추가
 양식 영역에 사용자 지정 작업을 추가 하려면 사용 합니다 **사용자 지정 작업** 대화 상자. 열 수 있습니다 합니다 **사용자 지정 작업** 대화 상자에서 양식 영역을 선택 하 여 **솔루션 탐색기**확장, 합니다 **매니페스트** 에서 노드를 **속성 창**선택 하 여 **Customaction** 속성 및 줄임표 단추를 클릭 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")).

 사용할 수는 **사용자 지정 작업** 지정 하려면 대화 상자를 *대상 폼*합니다. 대상 형식은 사용자 지정 작업을 실행할 때 표시 되는 형식입니다.

 사용할 수도 있습니다는 **사용자 지정 작업** 대화 상자를 원하는 대상 형식으로 표시 하려면 원래 항목의에서 정보를 지정 합니다.

 다음 표에서 사용할 수 있는 속성을 **사용자 지정 작업** 대화 상자.

|속성|설명|
|--------------|-----------------|
|**AddressLike**|대상 폼은 해결 하는 방법을 지정 합니다.|
|**본문**|대상 폼에 원래 항목의 본문은 추가 하는 방법을 지정 합니다.|
|**사용**|사용자 지정 작업 사용 되는지 여부를 나타냅니다. 이 속성 설정 된 경우 **false**, 사용자 지정 작업은 사용 하지 않도록 설정 합니다.|
|**메서드**|사용자 지정 작업을 실행할 때 사용 가능한 응답 형식을 지정 합니다. 사용자 지정 작업 폼을 전송 하 고 폼을 열어 하 하거나 묻는 메시지를 보내거나 양식을 엽니다 것인지 여부를 수 있습니다.|
|**이름**|코드에서이 사용자 지정 작업을 참조 하는 데 사용할 수 있는 내부 이름을 지정 합니다.|
|**ShowOnRibbon**|원래 항목의 리본에 사용자 지정 작업을 표시할지 여부를 나타냅니다.|
|**SubjectPrefix**|대상 폼의 제목 줄의 시작 부분에 삽입 되는 텍스트를 지정 합니다.|
|**TargetForm**|대상 폼의 메시지 클래스 이름을 지정합니다. 예를 들어 입력 **IPM 합니다. 작업** 태스크 폼을 엽니다.|
|**제목**|사용자 지정 작업 단추가의 레이블을 지정합니다.|

## <a name="customize-a-custom-action-at-runtime"></a>런타임 시 사용자 지정 동작을 사용자 지정
 또한 코드를 사용 하 여 사용자 지정 작업 동작을 추가할 수 있습니다. 예를 들어 전자 메일 받는 사람 이름을 사용 하 고 새 약속 항목의 참석자로 해당 이름을 추가 하는 코드를 추가할 수 있습니다. 이 위해 처리 합니다 [CustomAction](/office/vba/api/Outlook.MailItem.CustomAction) 이벤트를 [MailItem 개체](/office/vba/api/Outlook.MailItem)합니다.

## <a name="see-also"></a>참고자료
- [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)
- [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.](../vsto/associating-a-form-region-with-an-outlook-message-class.md)
