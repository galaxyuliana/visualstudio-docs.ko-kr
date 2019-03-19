---
title: SCRIPTUICITEM 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fbf01f1b-5d7f-4d92-8d10-3da65e352d93
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd454780b4360daf844697ad92ab8a4e9da29317
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151988"
---
# <a name="scriptuicitem-enumeration"></a>SCRIPTUICITEM 열거형
UI 항목의 유형을 나타냅니다. 에 사용 된 [iactivescriptsiteuicontrol:: Getuibehavior 메서드](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
typedef enum tagSCRIPTUICITEM {     SCRIPTUICITEM_INPUTBOX = 1,     SCRIPTUICITEM_MSGBOX = 2,     } SCRIPTUICITEM;   
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTUICITEM_INPUTBOX|입력된 컨트롤입니다.|  
|SCRIPTUICITEM_MSGBOX|메시지 상자입니다.|