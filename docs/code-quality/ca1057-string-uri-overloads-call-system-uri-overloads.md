---
title: 'CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 41d3db6e4807c77236868e3ab5746da971ddce6c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922486"
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.

|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

형식은 <xref:System.Uri?displayProperty=fullName> 매개 변수를 사용 하 여 문자열 매개 변수를 대체 하는 것만 다르고 문자열 매개 변수를 사용 하는 오버 로드는 매개 변수를 <xref:System.Uri> 사용 하는 오버 로드를 호출 하지 않는 메서드 오버 로드를 선언 합니다.

## <a name="rule-description"></a>규칙 설명
오버 로드는 문자열 또는 <xref:System.Uri> 매개 변수만 다르므로 문자열은 URI (uniform resource identifier)를 나타내는 것으로 간주 됩니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. 클래스 <xref:System.Uri> 는 안전 하 고 안전한 방식으로 이러한 서비스를 제공 합니다. <xref:System.Uri> 클래스의 이점을 활용 하려면 문자열 오버 로드에서 문자열 인수를 사용 하 <xref:System.Uri> 여 오버 로드를 호출 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
URI의 문자열 표현을 사용 하는 메서드를 다시 구현 하 여 문자열 인수를 사용 하 여 <xref:System.Uri> 클래스의 인스턴스를 만든 다음 <xref:System.Uri> 매개 변수를 포함 <xref:System.Uri> 하는 오버 로드에 개체를 전달 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
문자열 매개 변수가 URI를 나타내지 않는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 올바르게 구현 된 문자열 오버 로드를 보여 줍니다.

[!code-csharp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CSharp/ca1057-string-uri-overloads-call-system-uri-overloads_1.cs)]
[!code-cpp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CPP/ca1057-string-uri-overloads-call-system-uri-overloads_1.cpp)]
[!code-vb[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/VisualBasic/ca1057-string-uri-overloads-call-system-uri-overloads_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA2234: 문자열 대신 System.uri 개체를 전달 합니다.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

[CA1056: URI 속성은 문자열이 면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

[CA1054: URI 매개 변수는 문자열이 면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

[CA1055: URI 반환 값은 문자열이 면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)