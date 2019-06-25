---
title: '방법: 편집기에서 포커스를 잃을 때 이벤트를 발생 시키는 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 57cc24847e0a7635c27a78e983b2bf46ed4326c5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340843"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>방법: 편집기에서 포커스를 잃을 때 이벤트 발생
경우에 따라 편집기 창 프레임에 포커스를 잃을 때 알아야 합니다. 예를 들어, 편집기에서 포커스를 잃을 후 코드 창에서 코드를 추출 해야 합니다. 다음 절차는 포커스를 잃는 편집기에 대 한 알림을 수신 하는 단계를 제공 합니다.

## <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>포커스를 잃는 편집기에 대 한 응답에서 이벤트를 발생 시키는

1. 확보 하 여 선택 이벤트를 모니터링 합니다.는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 에서 개체 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>합니다.

2. 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> 제공 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> 개체입니다.

3. 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>를 검색할 `elementid==SEID_WindowFrame`합니다.

4. 테스트는 `varValueNew` 두 가지에 대 한 매개 변수:

    1. 찾고자 하는 창 프레임입니다.

    2. 프로그램의 선택 영역 창 프레임을 손실는 점입니다.