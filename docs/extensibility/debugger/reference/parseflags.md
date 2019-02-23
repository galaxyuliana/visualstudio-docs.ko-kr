---
title: PARSEFLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 56ba1933d1b63f9af863b115972f3ecf1dfc4346
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695715"
---
# <a name="parseflags"></a>PARSEFLAGS
식의 구문을 분석 하는 방법을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
typedef DWORD PARSEFLAGS;
```

```csharp
public enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
```

## <a name="members"></a>멤버
 PARSE_EXPRESSION 식 문 임을 나타냅니다.

 PARSE_FUNCTION_AS_ADDRESS 주소로 식이 구문 분석 (및 나중에 계산)를 나타냅니다.

 식이 디자인 타임 동안 구문 분석 되는 PARSE_DESIGN_TIME_EXPR_EVAL 나타냅니다 (즉, 디자이너를 열 때).

## <a name="remarks"></a>설명
 매개 변수로 전달 합니다 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 하 고 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 메서드.

## <a name="requirements"></a>요구 사항
 헤더: msdbg.h

 네임스페이스: Microsoft.VisualStudio.Debugger.Interop

 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)