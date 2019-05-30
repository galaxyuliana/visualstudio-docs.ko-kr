---
title: IDebugStackFrame2::GetLanguageInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d220e3c1d9e7b5879d12ed31f6a3374e6c481fe3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352141"
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
이 스택 프레임과 연결 된 언어를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetLanguageInfo ( 
   BSTR* pbstrLanguage,
   GUID* pguidLanguage
);
```

```csharp
int GetLanguageInfo ( 
   ref string pbstrLanguage,
   ref Guid   pguidLanguage
);
```

## <a name="parameters"></a>매개 변수
`pbstrLanguage`\
[out] 이 스택 프레임과 연결 된 메서드를 구현 하는 언어의 이름을 반환 합니다.

`pguidLanguage`\
[out] 반환 된 `GUID` 언어입니다. 에 대 한는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 언어, 예를 들어, 다음 돌아오게 됩니다.

-   `guidVBScriptLang`\

-   `guidJScriptLang`\

-   `guidCPPLang`\

-   `guidVBLang`\

-   `guidSQLLang`\

-   `guidScriptLang`\

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고자료
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)