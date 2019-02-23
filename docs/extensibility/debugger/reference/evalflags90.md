---
title: EVALFLAGS90 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 73673d0b0ca7ccb640a3fab2043bc35b26657a9b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720304"
---
# <a name="evalflags90"></a>EVALFLAGS90
식 계산을 제어 하는 플래그에 대 한 유효한 값을 열거 합니다. 이 열거형을 확장 합니다 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 열거형입니다.

## <a name="syntax"></a>구문

```cpp
enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
typedef DWORD EVALFLAGS90;
```

```csharp
public enum enum_EVALFLAGS90
{
    // VS 8.0 values
    EVAL90_RETURNVALUE                 = 0x0002,
    EVAL90_NOSIDEEFFECTS               = 0x0004,
    EVAL90_ALLOWBPS                    = 0x0008,
    EVAL90_ALLOWERRORREPORT            = 0x0010,
    EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,
    EVAL90_NOFUNCEVAL                  = 0x0080,
    EVAL90_NOEVENTS                    = 0x1000,
    EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,
    EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,

    // Values added in VS 9.0
    EVAL90_FORCE_EVALUATION_NOW        = 0x8000
};
```

#### <a name="parameters"></a>매개 변수
EVAL90_RETURNVALUE 있으면 반환 값을 평가 하는 것을 지정 합니다.

EVAL90_NOSIDEEFFECTS 의도 하지 수 있도록 지정 합니다.

EVAL90_ALLOWBPS 중단점에서 중지를 지정 합니다.

EVAL90_ALLOWERRORREPORT 해당 오류 수를 보고 호스트를 지정 합니다. Internet Explorer에서 스크립트의 식 평가 위해 주로 사용 됩니다.

함수를 호출 하는 대신 주소로 평가할 EVAL90_FUNCTION_AS_ADDRESS 강제로 함수입니다.

평가 EVAL90_NOFUNCEVAL 방지 함수입니다. 예를 들어 합니다 `int` 식에서 토큰 `myExpression(int) + 10`합니다. 이 함수는 주소로 아니지만 값을 올바르게 평가할 수 있습니다.

식 평가 중 발생 하는 이벤트를 보내지 세션 디버그 관리자 (SDM) 또는 IDE를 나타내기 위해 EVAL90_NOEVENTS 플래그입니다.

디자인 타임 식 계산 EVAL90_DESIGN_TIME_EXPR_EVAL 사용 하도록 설정 합니다.

EVAL90_ALLOW_IMPLICIT_VARS 허용 암시적 변수 생성 합니다.

즉시 실행 되도록 EVAL90_FORCE_EVALUATION_NOW 강제로 평가 합니다. 사용자 요청과 같이 요청을 서비스 하는 경우에 유용 합니다.

## <a name="requirements"></a>요구 사항
헤더: Msdbg90.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
- [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
