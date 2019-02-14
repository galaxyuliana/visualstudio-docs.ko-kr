---
title: WriteContextTLogs | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- WriteContextTLogs
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- WriteContextTLogs
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: deee2af2ccf1f2561410bc66b7f2f096bab61dd5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54764939"
---
# <a name="writecontexttlogs"></a>WriteContextTLogs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
현재 컨텍스트에 대한 로그 파일을 작성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 [in] `tlogRootName`  
 로그 파일 이름의 루트 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 추적 컨텍스트가 만들어진 경우 SUCCEEDED 비트가 설정된 <!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->HRESULT<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h  
  
## <a name="see-also"></a>참고 항목  
 [WriteAllTLogs](../msbuild/writealltlogs.md)
