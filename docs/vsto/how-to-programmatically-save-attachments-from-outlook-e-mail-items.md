---
title: '방법: 프로그래밍 방식으로 Outlook 전자 메일 항목의 첨부 파일 저장'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 874f19e0ae4e752a36ce95deab669ab46bfbf038
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419505"
---
# <a name="how-to-programmatically-save-attachments-from-outlook-email-items"></a>방법: 프로그래밍 방식으로 Outlook 전자 메일 항목의 첨부 파일 저장
  이 예제는 받은 편지함에 전자 메일이 수신될 때 메일 첨부 파일을 지정된 폴더에 저장합니다.

> [!IMPORTANT]
> 이 예제에서는 라는 폴더를 추가 하는 경우에 작동 **TestFileSave** C 디렉터리의 루트에 있습니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>예제
 [!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]

## <a name="see-also"></a>참고자료
- [메일 항목 작업](../vsto/working-with-mail-items.md)
- [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [방법: 프로그래밍 방식으로 전자 메일 메시지를 받으면 작업을 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
- [방법: 프로그래밍 방식으로 특정 폴더 내용 검색](../vsto/how-to-programmatically-search-within-a-specific-folder.md)
