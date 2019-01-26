---
title: SccRemove 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccRemove
helpviewer_keywords:
- SccRemove function
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4db8360f6874f8e2c506aefb153c663670fa5cba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014837"
---
# <a name="sccremove-function"></a>SccRemove 함수
이 함수는 소스 제어 시스템에서 파일을 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 원본 제어 플러그 인 상황에 맞는 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 [in] 에 지정 된 파일 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 [in] 제거할 파일의 정규화 된 로컬 경로 이름 배열입니다.  
  
 lpComment  
 [in] 제거할 각 파일에 적용할 주석입니다.  
  
 fOptions  
 [in] 명령 플래그 (사용 되지 않는)입니다.  
  
 pvOptions  
 [in] 원본 제어 플러그 인에 대 한 옵션입니다.  
  
## <a name="return-value"></a>반환 값  
 원본 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환 하:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|제거 성공 했습니다.|  
|SCC_E_FILENOTCONTROLLED|선택한 파일이 소스 제어 없습니다.|  
|SCC_E_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC_E_ISCHECKEDOUT|사용자가 체크 아웃 하기 때문에 파일을 제거할 수 없습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제로 인해 액세스 문제가 있습니다.|  
|SCC_E_NOTAUTHORIZED|사용자는이 작업을 수행할 수 없습니다.|  
|SCC_E_NONSPECIFICERROR|일반 오류입니다. 파일 제거 되지 않았습니다.|  
|SCC_I_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는 소스 제어 시스템에서 파일을 제거 하지만 사용자의 로컬 하드 드라이브에서 삭제 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)