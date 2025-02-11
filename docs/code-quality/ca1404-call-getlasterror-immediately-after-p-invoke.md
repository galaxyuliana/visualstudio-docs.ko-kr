---
title: 'CA1404: P/Invoke 다음에 바로 GetLastError를 호출하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 03add1625c4d59bb180f9f0f08692e67bee8047b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922074"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: P/Invoke 다음에 바로 GetLastError를 호출하십시오.

|||
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> 메서드나 이와 동등한 Win32 `GetLastError` 함수를 호출 하 고 바로 앞에 오는 호출은 플랫폼 호출 메서드에 적용 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
플랫폼 호출 메서드는 비관리 코드에 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 액세스 하 고 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성의 키워드를 사용 하 여 정의 됩니다. 일반적으로 오류가 발생 하면 관리 되지 않는 함수는 `SetLastError` Win32 함수를 호출 하 여 오류와 연결 된 오류 코드를 설정 합니다. 실패 한 함수의 호출자는 Win32 `GetLastError` 함수를 호출 하 여 오류 코드를 검색 하 고 오류의 원인을 확인 합니다. 오류 코드는 스레드별 기준으로 유지 관리 되며,에 대 `SetLastError`한 다음 호출로 덮어쓰여집니다. 실패 한 플랫폼 호출 메서드를 호출한 후에는 관리 코드에서 메서드를 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 호출 하 여 오류 코드를 검색할 수 있습니다. 다른 관리 되는 클래스 라이브러리 메서드의 `GetLastError` 내부 호출로 오류 코드를 덮어쓸 수 있기 때문에 플랫폼 호출 메서드를 호출한 직후 또는 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드를 호출 해야 합니다.

규칙은 플랫폼 호출 메서드 호출과 호출 사이에 발생 하는 경우 다음 관리 되는 멤버에 대 한 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>호출을 무시 합니다. 이러한 멤버는 오류 코드를 변경 하지 않으며 일부 플랫폼 호출 메서드 호출의 성공 여부를 확인 하는 데 유용 합니다.

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 플랫폼 호출 메서드에 대 한 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 호출 바로 뒤에 오는 호출을로 이동 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
플랫폼 호출 메서드 호출과 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드 호출 사이의 코드에서 명시적으로 또는 암시적으로 오류 코드를 변경 하지 못할 경우에는이 규칙에서 경고를 표시 하지 않아도 됩니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 메서드와 규칙을 충족 하는 메서드를 보여 줍니다.

[!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
[!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA1060: P/Invoke를 NativeMethods 클래스로 이동](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

[CA1400: P/Invoke 진입점이 있어야 합니다.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

[CA1401: P/Invoke는 노출 되지 않아야 합니다.](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

[CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

[CA2205: Win32 API의 관리 되는 항목 사용](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)