---
title: 'CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8e8d47b73009e0bd742c989ddc0311644453e5d9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921862"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하세요.

|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
플랫폼 호출 메서드 선언에 <xref:System.Boolean?displayProperty=fullName> 매개 변수 또는 반환 값이 포함 되어 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> 있지만 특성이 매개 변수 또는 반환 값에 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
플랫폼 호출 메서드는 비관리 코드에 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 액세스 하 고 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>의 키워드를 사용 하 여 정의 됩니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute>관리 코드와 비관리 코드 간에 데이터 형식을 변환 하는 데 사용 되는 마샬링 동작을 지정 합니다. <xref:System.Byte?displayProperty=fullName> 및<xref:System.Int32?displayProperty=fullName>와 같은 많은 단순 데이터 형식은 비관리 코드에서 단일 표현을 가지 며 마샬링 동작을 지정 하지 않아도 됩니다. 공용 언어 런타임에서 올바른 동작을 자동으로 제공 합니다.

<xref:System.Boolean> 데이터 형식은 비관리 코드에 여러 개의 표현이 있습니다. 을 지정 하지 않은 경우 <xref:System.Boolean> 데이터 형식 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>에 대 한 기본 마샬링 동작은입니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 이것은 모든 상황에서 적절 하지 않은 32 비트 정수입니다. 관리 되지 않는 메서드에 필요한 부울 표현을 결정 하 고 적절 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>하 게 일치 해야 합니다. Unmanagedtype.lpwstr은 항상 4 바이트인 Win32 BOOL 형식입니다. Unmanagedtype.lpwstr는 또는 다른 1 바이트 형식 C++ `bool` 에 사용 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 <xref:System.Runtime.InteropServices.MarshalAsAttribute> <xref:System.Boolean> 매개 변수 또는 반환 값에을 적용 합니다. 특성의 값을 적절 한 <xref:System.Runtime.InteropServices.UnmanagedType>로 설정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다. 기본 마샬링 동작이 적절 한 경우에도 동작이 명시적으로 지정 되 면 코드를 보다 쉽게 유지할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 적절 한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성으로 표시 된 플랫폼 호출 메서드를 보여 줍니다.

[!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
[!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
[!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]

## <a name="related-rules"></a>관련 규칙
[CA1901: P/Invoke 선언은 이식 가능 해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

[CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)