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
ms.openlocfilehash: 1a06197278c61a25c4baad15888f818ed1e1f673
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955885"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하세요.

|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 플랫폼 호출 메서드 선언에 포함 된 <xref:System.Boolean?displayProperty=fullName> 매개 변수나 반환 값 하지만 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> 특성 매개 변수 또는 반환 값에 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 플랫폼 메서드가 관리 되지 않는 코드에 액세스를 호출 하 고 사용 하 여 정의 되는 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 관리 및 비관리 코드 간에 데이터 형식을 변환 하는 데 사용 되는 마샬링 동작을 지정 합니다. 와 같은 여러 단순 데이터 형식은 <xref:System.Byte?displayProperty=fullName> 고 <xref:System.Int32?displayProperty=fullName>; 올바른 동작 기본적으로 제공 하는 공용 언어 런타임, 관리 되지 않는 코드를 단일 표현에 및의 마샬링 동작을 지정할 필요가 없습니다.

 <xref:System.Boolean> 데이터 형식을 관리 되지 않는 코드에 대 한 여러 표현 합니다. 경우는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 지정 하지 않으면 기본 마샬링 동작에 대 한 합니다 <xref:System.Boolean> 데이터 형식은 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>합니다. 이 32 비트 정수를 모든 상황에 적합 하지 않습니다. 관리 되지 않는 메서드에서 요구 하는 부울 표현을 결정 하 고 적절 한 일치 해야 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>합니다. UnmanagedType.Bool은 항상 4 바이트 Win32 BOOL 형식,입니다. C + +에 사용할 UnmanagedType.U1 `bool` 또는 다른 1 바이트 형식입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적용 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 에 <xref:System.Boolean> 매개 변수나 반환 값입니다. 적절 한 특성의 값을 설정할 <xref:System.Runtime.InteropServices.UnmanagedType>합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 적절 한 기본 마샬링 동작 경우 동작을 명시적으로 지정 하는 경우 코드를 더 쉽게 유지 됩니다.

## <a name="example"></a>예제

다음 예제에서는 적절 한 표시 되는 메서드를 호출 하는 플랫폼 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성입니다.

 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]

## <a name="related-rules"></a>관련된 규칙
 [CA1901: P/Invoke 선언은 이식 가능 해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

 [CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)