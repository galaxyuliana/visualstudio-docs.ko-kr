---
title: ResumeTracking | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f0bc04dfa06672e7764676be87584c2a757a50b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54940585"
---
# <a name="resumetracking"></a>ResumeTracking
현재 컨텍스트에서 추적을 다시 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>반환 값  
 추적이 다시 시작된 경우 **SUCCEEDED** 비트가 설정된 **HRESULT**를 반환합니다. 컨텍스트를 사용할 수 없어 추적을 다시 시작할 수 없는 경우 **E_FAIL**이 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** *FileTracker.h*  
  
## <a name="see-also"></a>참고 항목  
 [SuspendTracking](../msbuild/suspendtracking.md)