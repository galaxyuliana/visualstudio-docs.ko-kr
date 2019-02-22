---
title: '방법: 프로그래밍 방식으로 사용자 지정 달력 만들기'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom calendars [Office development in Visual Studio]
- calendars [Office development in Visual Studio], custom
- appointments [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 653340d3a682664670998c874344bfc931105892
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624778"
---
# <a name="how-to-programmatically-create-a-custom-calendar"></a>방법: 프로그래밍 방식으로 사용자 지정 달력 만들기
  이 예제에서는 라는 새 달력 폴더를 만듭니다 **PersonalCalendar**, 새 약속 항목을 만든 다음 및 일정 폴더에 추가 합니다. 그런 다음 일정 폴더를 표시 합니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>예제
 [!code-csharp[Trin_OL_CustomCalendar#1](../vsto/codesnippet/CSharp/Trin_OL_CustomCalendar/thisaddin.cs#1)]

## <a name="see-also"></a>참고자료
- [달력 항목 작업](../vsto/working-with-calendar-items.md)
- [방법: 프로그래밍 방식으로 약속 만들기](../vsto/how-to-programmatically-create-appointments.md)
- [방법: 프로그래밍 방식으로 모임 요청 만들기](../vsto/how-to-programmatically-create-a-meeting-request.md)
