---
title: 'CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d1eb4c2535060f9a110d149e88ac2532e6ad1412
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921094"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.

|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|범주|Microsoft.Globalization|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
플랫폼 호출 멤버는 부분적으로 신뢰할 수 있는 호출자를 허용 하 고 문자열 매개 변수를 포함 하며 문자열을 명시적으로 마샬링할 수 없습니다.

## <a name="rule-description"></a>규칙 설명
유니코드에서 ANSI로 변환 하는 경우 특정 ANSI 코드 페이지에서 모든 유니코드 문자를 표현할 수 있는 경우가 있습니다. *최적 매핑은* 표현할 수 없는 문자를 문자로 대체 하 여이 문제를 해결 하려고 시도 합니다. 이 기능을 사용 하면 선택한 문자를 제어할 수 없기 때문에 보안상 위험할 수 있습니다. 예를 들어 악의적인 코드는 특정 코드 페이지에서 찾을 수 없는 문자를 포함 하는 유니코드 문자열을 의도적으로 만들 수 있으며,이는 '. '와 같이 파일 시스템 특수 문자로 변환 됩니다. 또는 '/'. 또한 특수 문자에 대 한 보안 검사는 문자열이 ANSI로 변환 되기 전에 자주 발생 합니다.

최적 매핑은 관리 되지 않는 변환의 기본값입니다. 최적 매핑을 명시적으로 사용 하지 않도록 설정 하지 않는 한 코드에는이 문제로 인해 악용 가능한 보안 취약성이 포함 될 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 문자열 데이터 형식을 명시적으로 마샬링합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙을 위반 하는 메서드를 보여 주고 위반 문제를 해결 하는 방법을 보여 줍니다.

[!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]