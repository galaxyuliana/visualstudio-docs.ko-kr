---
title: IDebugSettingsCallback2::GetEEMetricDword | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricDword
ms.assetid: c5f8f417-0ef0-4fd0-a779-b0a8ead4effe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e5f090d2000c26ff1fc0e008c46e6988430755d2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935386"
---
# <a name="idebugsettingscallback2geteemetricdword"></a>IDebugSettingsCallback2::GetEEMetricDword
식 계산기의 지정 된 메트릭을에 해당 하는 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEEMetricDword(  
   REFGUID guidLang,  
   REFGUID guidVendor,  
   LPCWSTR pszMetric,  
   DWORD*  pdwValue  
);  
```  
  
```csharp  
private int GetEEMetricDword(  
   ref Guid guidLang,  
   ref Guid guidVendor,  
   string   pszMetric,  
   out uint pdwValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidLang`  
 [in] 프로그래밍 언어의 고유 식별자입니다.  
  
 `guidVendor`  
 [in] 공급 업체의 고유 식별자입니다.  
  
 `pszMetric`  
 [in] 메트릭의 이름입니다.  
  
 `pdwValue`  
 [out] 메트릭 문자열에 해당 하는 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)