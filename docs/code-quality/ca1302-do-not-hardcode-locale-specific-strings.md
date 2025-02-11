---
title: 'CA1302: 로캘별 문자열을 하드코드하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0b3789b5e786038c2bf1fe5e823a1b0fb4f7a7c9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922721"
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: 로캘별 문자열을 하드코드하지 마세요.

|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|범주|Microsoft.Globalization|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
메서드는 특정 시스템 폴더의 경로 부분을 나타내는 문자열 리터럴을 사용 합니다.

## <a name="rule-description"></a>규칙 설명
<xref:System.Environment.SpecialFolder?displayProperty=fullName> 열거형에는 특수 시스템 폴더를 참조 하는 멤버가 포함 되어 있습니다. 이러한 폴더의 위치는 다른 운영 체제에서 다른 값을 가질 수, 사용자 위치 중 일부를 변경할 수 및 위치는 지역화 합니다. 특수 폴더의 예는 "C:\WINNT\system32 system32" [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] 이지만의 [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]"" 인 시스템 폴더입니다. 메서드 <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> 는 <xref:System.Environment.SpecialFolder> 열거형과 연결 된 위치를 반환 합니다. 에서 <xref:System.Environment.GetFolderPath%2A> 반환 되는 위치는 지역화 되어 현재 실행 중인 컴퓨터에 적합 합니다.

이 규칙은 메서드를 <xref:System.Environment.GetFolderPath%2A> 사용 하 여 검색 된 폴더 경로를 별도의 디렉터리 수준으로 토큰화 합니다. 각 문자열 리터럴은 토큰과 비교 됩니다. 일치 하는 항목이 있으면 메서드에서 토큰과 연결 된 시스템 위치를 참조 하는 문자열을 작성 하는 것으로 가정 합니다. 이식성 및 지역화 가능성을 위해 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용 하 여 문자열 리터럴을 사용 하는 대신 특수 시스템 폴더의 위치를 검색 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용 하 여 위치를 검색 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
문자열 리터럴이 <xref:System.Environment.SpecialFolder> 열거와 연결 된 시스템 위치 중 하나를 참조 하는 데 사용 되지 않는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는이 규칙에서 3 개의 경고를 생성 하는 공용 응용 프로그램 데이터 폴더의 경로를 작성 합니다. 그런 다음 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용 하 여 경로를 검색 합니다.

[!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
[!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA1303: 리터럴을 지역화 된 매개 변수로 전달 하지 마십시오.](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)