---
title: SetThreadCount | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- SetThreadCount
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6a57ac0b3412c6668dea1669d14b72fe399b6ab2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758628"
---
# <a name="setthreadcount"></a>SetThreadCount
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
전역 스레드 개수를 설정하고 해당 개수를 현재 스레드에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `threadCount`  
 사용할 스레드 수입니다.  
  
## <a name="return-value"></a>반환 값  
 스레드 개수가 업데이트된 경우 [SUCCEEDED](<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 비트가 설정된 [HRESULT](<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->)를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h
