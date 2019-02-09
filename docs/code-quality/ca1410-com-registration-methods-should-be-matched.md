---
title: 'CA1410: COM 등록 메서드는 일치해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c606a55be00ac8e44d54bad289076498e2655af1
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913342"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM 등록 메서드는 일치해야 합니다.

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식으로 표시 되는 메서드를 선언 합니다 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성으로 표시 되는 메서드를 선언 하지 않습니다 하지만 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성 또는 그 반대로 합니다.

## <a name="rule-description"></a>규칙 설명
 .NET Framework 형식을 만드는 구성 요소 개체 모델 (COM) 클라이언트용 형식은 먼저 등록 되어야 합니다. 사용 가능한 경우로 표시 된 메서드는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 특성 사용자 지정 코드를 실행 하는 등록 프로세스 동안 호출 됩니다. 로 표시 된 해당 메서드는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 등록 메서드 작업을 되돌리기 위해 등록 프로세스 동안 특성 이라고 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 해당 등록 또는 등록 취소 메서드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다. 코드를 주석 처리 된 위반에 대 한 수정 프로그램을 보여 줍니다.

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>관련된 규칙
 [CA1411: COM 등록 메서드를 표시 해야 합니다.](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [COM에 어셈블리 등록](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe(어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)