---
title: IDebugCodeContext2::GetLanguageInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCodeContext2::GetLanguageInfo
helpviewer_keywords:
- IDebugCodeContext2::GetLanguageInfo
ms.assetid: 03002ef1-9fe6-44b6-b23b-ef7b86b2b21b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e4afcb2a8fd9de89b74fccec373e71e19264fe56
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712491"
---
# <a name="idebugcodecontext2getlanguageinfo"></a>IDebugCodeContext2::GetLanguageInfo
이 코드 컨텍스트에 대 한 언어 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetLanguageInfo( 
   BSTR* pbstrLanguage,
   GUID* pguidLanguage
);
```

```csharp
int GetLanguageInfo( 
   ref string pbstrLanguage,
   ref Guid pguidLanguage
);
```

#### <a name="parameters"></a>매개 변수
 `pbstrLanguage`

 [out에서] "C + +입니다."와 같은 언어의 이름을 포함 하는 문자열을 반환 합니다.

 `pguidLanguage`

 [out에서] 예를 들어 코드 컨텍스트에의 언어에 대 한 GUID를 반환 합니다 `guidCPPLang`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 하나 이상의 매개 변수는 null이 아닌 값을 반환 해야 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)