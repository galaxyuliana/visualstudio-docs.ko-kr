---
title: SuspendTracking | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a093b89264df43574acd3929d4370bb43162d829
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54946752"
---
# <a name="suspendtracking"></a>SuspendTracking
현재 컨텍스트에서 추적을 일시 중단합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp 
HRESULT WINAPI SuspendTracking(void);  
```  
  
## <a name="return-value"></a>반환 값  
 추적이 일시 중단된 경우 **SUCCEEDED** 비트가 설정된 **HRESULT**를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** *FileTracker.h*  
  
## <a name="see-also"></a>참고 항목  
 [ResumeTracking](../msbuild/resumetracking.md)