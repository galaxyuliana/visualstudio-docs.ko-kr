---
title: IDebugSettingsCallback2::GetEEMetricFile | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricFile
ms.assetid: 3a0bf9e5-bbd2-4d15-840d-8244732787fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e800d8d57d34c0ed99cb3cfa9a3f6a7b871a034d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458600"
---
# <a name="idebugsettingscallback2geteemetricfile"></a>IDebugSettingsCallback2::GetEEMetricFile
이름 또는 메트릭을 지정 된 식 계산기 메트릭 파일을 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetEEMetricFile(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   BSTR*   pbstrValue
);
```

```csharp
private int GetEEMetricFile(
   ref Guid   guidLang,
   ref Guid   guidVendor,
   string     pszMetric,
   out string pbstrValue
);
```

## <a name="parameters"></a>매개 변수
 `guidLang`\

 [in] 프로그래밍 언어의 고유 식별자입니다.

 `guidVendor`\

 [in] 공급 업체의 고유 식별자입니다.

 `pszMetric`\

 [in] 메트릭의 이름입니다.

 `pbstrValue`\

 [out] 메트릭 파일의 내용을 문자열로 반환합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)