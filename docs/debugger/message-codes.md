---
title: 메시지 코드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c3899da3b668406a701ce5c1c4935b531754d10e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017086"
---
# <a name="message-codes"></a>메시지 코드
에 표시 된 각 메시지 줄 [메시지 보기](../debugger/messages-view.md) 'P'를 포함의 '의 ' 또는 'R' 코드입니다. 이러한 코드에는 다음과 같은 의미가 있습니다.  
  
|코드|의미|  
|----------|-------------|  
|P|메시지가 큐로 게시 합니다 **PostMessage** 함수입니다. 없는 정보 메시지의 최종 처리와 관련 된 제공 됩니다.|  
|S|사용 하 여 메시지를 보낸 합니다 **SendMessage** 함수입니다. 즉, 보낸 사람에 게는 수신자 처리 하 고 메시지를 반환 될 때까지 컨트롤을 다시 하지 않습니다. 따라서 수신자 보낸 사람에 게 반환 값을 전달할 수 있습니다.|  
|s|메시지를 보냈지만 보안 반환 값에 대 한 액세스를 방지 합니다.|  
|R|각각의 ' 줄에는 해당 'R' (반환) 줄 메시지 반환 값을 나열 합니다. 경우에 따라 메시지 호출이 중첩 되는, 즉, 하나의 메시지 처리기는 다른 메시지를 보냅니다.|