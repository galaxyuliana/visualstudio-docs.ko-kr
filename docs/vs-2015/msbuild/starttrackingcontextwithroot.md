---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- StartTrackingContextWithRoot
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e35384af02ad2fb5f3c15d1851cdc716bc29445b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787174"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
루트 마커를 지정하는 지시 파일을 사용하여 추적 컨텍스트를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 [in] `taskName`  
 추적 컨텍스트를 식별합니다. 이 이름은 로그 파일 이름을 만드는 데 사용됩니다.  
  
 [in] `rootMarkerResponseFile`  
 루트 마커가 포함된 지시 파일의 경로 이름입니다. 루트 이름은 컨텍스트에 대한 모든 추적을 그룹화하는 데 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 추적 컨텍스트가 만들어진 경우 SUCCEEDED 비트가 설정된 <!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->HRESULT<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h  
  
## <a name="see-also"></a>참고 항목  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)
