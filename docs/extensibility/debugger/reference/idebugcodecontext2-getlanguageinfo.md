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
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8e2ecbd9e33eaf43df9937eabd7d9149d3e85f4d
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206737"
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

## <a name="parameters"></a>매개 변수
`pbstrLanguage`\
[out에서] 같은 언어의 이름을 포함 하는 문자열을 반환 합니다. "C++."

`pguidLanguage`\
[out에서] 예를 들어 코드 컨텍스트에의 언어에 대 한 GUID를 반환 합니다 `guidCPPLang`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>설명
 하나 이상의 매개 변수는 null이 아닌 값을 반환 해야 합니다.

## <a name="see-also"></a>참고자료
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)