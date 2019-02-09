---
title: Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3a7833ecd2245e9acaa7c4bc35189bd5c9069daf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922045"
---
# <a name="associate-a-form-region-with-an-outlook-message-class"></a>Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.
  각 항목의 메시지 클래스를 사용 하 여 양식 영역을 연결 하 여 양식 영역을 표시 하는 Microsoft Office Outlook 항목을 지정할 수 있습니다. 예를 들어, 메일 항목의 맨 아래에 양식 영역을 추가 하려는 경우 양식 영역을 연결할 수는 `IPM.Note` message 클래스입니다.  
  
 메시지 클래스를 사용 하 여 양식 영역을 연결할 메시지 클래스 이름 지정는 **새 Outlook 양식 영역** 마법사 또는 양식 영역 팩터리 클래스에 특성을 적용 합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understand-outlook-message-classes"></a>Outlook 메시지 클래스 이해  
 Outlook 메시지 클래스에는 Outlook 항목의 형식을 식별 합니다. 다음 표에서 이러한 8 표준 항목 형식 및 해당 메시지 클래스 이름을 나열합니다.  
  
|Outlook 항목 형식|메시지 클래스 이름|  
|-----------------------|------------------------|  
|AppointmentItem|`IPM.Appointment`|  
|ContactItem|`IPM.Contact`|  
|DistListItem|`IPM.DistList`|  
|JournalItem|`IPM.Activity`|  
|MailItem|`IPM.Note`|  
|PostItem|`IPM.Post` 또는 `IPM.Post.RSS`|  
|TaskItem|`IPM.Task`|  
  
 또한 사용자 지정 메시지 클래스의 이름을 지정할 수 있습니다. 사용자 지정 메시지 클래스에는 Outlook에서 정의 하는 사용자 지정 양식을 식별 합니다.  
  
> [!NOTE]  
>  바꾸기 및 모두 바꾸기 양식 영역에 대 한 새 사용자 지정 메시지 클래스 이름을 지정할 수 있습니다. 기존 사용자 지정 폼의 메시지 클래스 이름을 사용할 필요가 없습니다. 사용자 지정 메시지 클래스의 이름은 고유 해야 합니다. 이름이 고유한 지 확인 하는 한 가지 방법은 다음과 비슷한 명명 규칙을 사용 하는 것입니다. \<*StandardMessageClassName*>.\< *회사*>.\< *MessageClassName*> (예: `IPM.Note.Contoso.MyMessageClass`).  
  
## <a name="associate-a-form-region-with-an-outlook-message-class"></a>Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.  
 두 가지 방법으로 메시지 클래스를 사용 하 여 양식 영역을 연결할 수 있습니다.  
  
-   사용 된 **새 Outlook 양식 영역** 마법사.  
  
-   클래스 특성을 적용 합니다.  
  
### <a name="use-the-new-outlook-form-region-wizard"></a>새 Outlook 양식 영역 마법사 사용  
 마지막 페이지에는 **새 Outlook 양식 영역** 마법사 표준 메시지 클래스를 선택 하 여 양식 영역과 연결 하려는 사용자 지정 메시지 클래스의 이름을 입력 합니다.  
  
 표준 메시지 클래스에서 양식 영역 전체 양식 또는 양식의 기본 페이지를 대체 하도록 고안 된 경우에 사용할 수 없는 경우 표준 메시지 클래스 이름을 양식에 새 페이지를 추가 하거나 폼의 맨 아래에 추가 된 양식에 대해서만 지정할 수 있습니다. 자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.  
  
 하나 이상의 사용자 지정 메시지 클래스를 포함 하려면에서 해당 이름을 입력 합니다 **이 양식 영역을 표시할 사용자 지정 메시지 클래스?** 상자입니다.  
  
 이름을 입력 하는 다음 지침을 준수 해야 합니다.  
  
- 정규화 된 메시지 클래스 이름 (예: "IPM.Note.Contoso").  
  
- 여러 메시지 클래스 이름을 구분 하려면 세미콜론을 사용 합니다.  
  
- "IPM와 같은 표준 Outlook 메시지 클래스를 포함 하지 않습니다. "또는"IPM 합니다. Contact "입니다. "IPM 등의 사용자 지정 메시지 클래스를 포함 합니다. Note.Contoso "로 설정 합니다.  
  
- 자체적으로 기본 메시지 클래스를 지정 하지 않으면 (예: "IPM").  
  
- 각 메시지 클래스 이름에 대해 256 자를 초과 하지.  
  
  합니다 **새 Outlook 양식 영역** 마법사를 클릭할 때 입력 형식의 유효성을 검사 **마침**합니다.  
  
> [!NOTE]  
>  합니다 **새 Outlook 양식 영역** 마법사에 제공 하는 메시지 클래스 이름을 올바름 또는 유효는 확인 하지 않습니다.  
  
 마법사를 완료 합니다 **새 Outlook 양식 영역** 마법사는 지정 된 메시지 클래스 이름을 포함 하는 양식 영역 클래스에 특성을 적용 합니다. 또한 이러한 특성을 수동으로 적용할 수 있습니다.  
  
### <a name="apply-class-attributes"></a>클래스 특성 적용  
 완료 한 후 Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결할 수 있습니다 합니다 **새 Outlook 양식 영역** 마법사. 이 작업을 수행 하려면 양식 영역 팩터리 클래스에 특성을 적용 합니다.  
  
 다음 예제에서는 두 개의 <xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute> 라는 양식 영역 팩터리 클래스에 적용 된 특성 `myFormRegion`합니다. 첫 번째 특성을 메일 메시지 형식에 대 한 표준 메시지 클래스를 사용 하 여 양식 영역을 연결합니다. 두 번째 특성 라는 사용자 지정 메시지 클래스를 사용 하 여 양식 영역 연결 `IPM.Task.Contoso`합니다.  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 특성 다음 지침을 준수 해야 합니다.  
  
- 사용자 지정 메시지 클래스에 대 한 정규화 된 메시지 클래스 이름을 사용 하 여 (예: "IPM.Note.Contoso").  
  
- 자체적으로 기본 메시지 클래스를 지정 하지 않으면 (예: "IPM").  
  
- 각 메시지 클래스 이름에 대해 256 자를 초과 하지.  
  
- 양식 영역 전체 양식 또는 양식의 기본 페이지를 대체 하는 경우에 표준 메시지 클래스의 이름이 포함 되지 않습니다. 표준 메시지 클래스 이름을 양식에 새 페이지를 추가 하거나 폼의 맨 아래에 추가 된 양식에 대해서만 지정할 수 있습니다. 자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.  
  
  Visual Studio 프로젝트를 빌드할 때의 메시지 클래스 이름 형식을 확인 합니다.  
  
> [!NOTE]  
>  Visual Studio에서 제공 하는 메시지 클래스 이름을 올바름 또는 유효는 확인 하지 않습니다.  
  
## <a name="see-also"></a>참고자료  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [형식 이름 및 메시지 클래스 개요](/office/vba/outlook/Concepts/Forms/form-name-and-message-class-overview)   
 [Outlook 양식 항목과 함께 작동](/office/vba/outlook/Concepts/Forms/how-outlook-forms-and-items-work-together)  
