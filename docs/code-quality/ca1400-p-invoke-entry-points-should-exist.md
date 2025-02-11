---
title: 'CA1400: P/Invoke 진입점이 있어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b292c58e666c11130fb25f67c234bfd2282fe463
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922249"
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: P/Invoke 진입점이 있어야 합니다.

|||
|-|-|
|TypeName|PInvokeEntryPointsShouldExist|
|CheckId|CA1400|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
Public 또는 protected 메서드는로 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>표시 됩니다. 관리되지 않는 라이브러리를 찾을 수 없거나 해당 메서드와 라이브러리의 함수가 일치하지 않습니다. 규칙에서 메서드 이름을 지정 된 대로 정확 하 게 찾을 수 없는 경우 메서드 이름을 ' A ' 또는 ' W '로 접미사로 하 여 메서드의 ANSI 또는 와이드 문자 버전을 찾습니다. 일치 하는 항목이 없는 경우 규칙은 __stdcall 이름 형식 (_MyMethod@12, 여기서 12는 인수의 길이를 나타냄)을 사용 하 여 함수를 찾으려고 시도 합니다. 일치 하는 항목이 없고 메서드 이름이 ' # '으로 시작 하는 경우 규칙은 이름 참조 대신 서 수 참조로 함수를 검색 합니다.

## <a name="rule-description"></a>규칙 설명
로 <xref:System.Runtime.InteropServices.DllImportAttribute> 표시 된 메서드가 참조 된 관리 되지 않는 DLL에 있는지 확인 하기 위해 컴파일 타임 검사를 사용할 수 없습니다. 지정 된 이름을 가진 함수가 라이브러리에 없거나 메서드의 인수가 함수 인수와 일치 하지 않으면 공용 언어 런타임에서 예외를 throw 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성이 있는 메서드를 수정 합니다. 관리 되지 않는 라이브러리가 있고 메서드를 포함 하는 어셈블리와 동일한 디렉터리에 있는지 확인 합니다. 라이브러리가 있고 올바르게 참조 되 면 메서드 이름, 반환 형식 및 인수 서명이 라이브러리 함수와 일치 하는지 확인 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
관리 되지 않는 라이브러리가이를 참조 하는 관리 되는 어셈블리와 동일한 디렉터리에 있는 경우에는이 규칙의 경고를 표시 하지 마십시오. 관리 되지 않는 라이브러리를 찾을 수 없는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다. 이라는 `DoSomethingUnmanaged` 함수는 kernel32.dll에서 발생 하지 않습니다.

[!code-csharp[FxCop.Interoperability.DLLExists#1](../code-quality/codesnippet/CSharp/ca1400-p-invoke-entry-points-should-exist_1.cs)]

## <a name="see-also"></a>참고자료
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>