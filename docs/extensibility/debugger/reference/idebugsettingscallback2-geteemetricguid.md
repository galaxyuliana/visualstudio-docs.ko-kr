---
title: IDebugSettingsCallback2::GetEEMetricGuid | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricGuid
ms.assetid: 3d70c19a-595d-44f1-a7b3-a0cf8f15e371
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f2bffa499d24bc38008982c990efd19205e95f6f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869033"
---
# <a name="idebugsettingscallback2geteemetricguid"></a>IDebugSettingsCallback2::GetEEMetricGuid
이름이 지정 된 식 계산기 메트릭에 대 한 고유 식별자를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetEEMetricGuid(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   GUID*   pguidValue
);
```

```csharp
HRESULT GetEEMetricGuid(
   ref Guid guidLang,
   ref Guid guidVendor,
   string   pszMetric,
   out Guid pguidValue
);
```

#### <a name="parameters"></a>매개 변수
 `guidLang`

 [in] 프로그래밍 언어의 고유 식별자입니다.

 `guidVendor`

 [in] 공급 업체의 고유 식별자입니다.

 `pszMetric`

 [in] 메트릭의 이름입니다.

 `pguidValue`

 [out] 메트릭의 고유 식별자를 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)