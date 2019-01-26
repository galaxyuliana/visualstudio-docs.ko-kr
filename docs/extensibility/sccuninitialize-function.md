---
title: SccUninitialize 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8dba45116c956c1edc1a8ffb691397375345c661
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967208"
---
# <a name="sccuninitialize-function"></a>SccUninitialize 함수
이 함수에 대 한 이전 호출에서 만든 연결 나 할당 정리 합니다 [SccInitialize](../extensibility/sccinitialize-function.md) 소스 제어 플러그 인 종료에 대 한 준비 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 원본 제어 플러그 인 상황에 맞는 구조에 대 한 포인터에서 생성 된 [SccInitialize](../extensibility/sccinitialize-function.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 원본 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환 하:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|정리 완료 되었습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인는 종료 하기 위해 준비 하 고 상황에 맞는 구조에 대 한 플러그 인에서 할당 메모리를 해제 합니다. 함수는 플러그 인 지정 된 각 인스턴스에 대해 한 번씩 호출 됩니다. 에 대 한 호출을 [SccInitialize](../extensibility/sccinitialize-function.md) 이 호출 앞에 옵니다. 프로젝트가 없으므로 계속 열 수에 대 한 호출 시 `SccUninitialize`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원본 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)