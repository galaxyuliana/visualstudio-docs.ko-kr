---
title: 'CA1411: COM 등록 메서드는 노출되면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4f6f40308255e0496b2bcccddf4299e83ea93100
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922046"
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411: COM 등록 메서드는 노출되면 안 됩니다.

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldNotBeVisible|
|CheckId|CA1411|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 특성으로표시된메서드는외부에서볼수있습니다.<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>

## <a name="rule-description"></a>규칙 설명
COM (구성 요소 개체 모델)을 사용 하 여 어셈블리를 등록 하면 어셈블리의 각 COM 노출 형식에 대해 레지스트리에 항목이 추가 됩니다. <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 및<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 특성으로 표시 된 메서드는 각각 등록 및 등록 취소 프로세스 중에 호출 되어 이러한 형식의 등록/등록 취소와 관련 된 사용자 코드를 실행 합니다. 이 코드는 이러한 프로세스 외부에서 호출 해서는 안 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 메서드의 `private` 액세스 가능성을 또는 `internal` (`Friend` 의 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]경우)로 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 두 개의 메서드를 보여 줍니다.

[!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
[!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA1410: COM 등록 메서드는 일치 해야 합니다.](../code-quality/ca1410-com-registration-methods-should-be-matched.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [COM에 어셈블리 등록](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe(어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)