---
title: 'CA2217: 열거형을 FlagsAttribute로 표시하지 마세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
dev_langs:
- VB
- CSharp
- CPP
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: abe9b53a02f5a2c12b734c793557c69868a973e8
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841509"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: 열거형을 FlagsAttribute로 표시하지 마세요.

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

열거형으로 표시 된 <xref:System.FlagsAttribute> 및 두 개 이상 있어 더 많은 값의 거듭제곱 두 또는 다른 조합 되지 않는 열거형에 값을 정의 합니다.

기본적으로이 규칙만 살펴봅니다 열거형 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

열거형 있어야 <xref:System.FlagsAttribute> 현재 열거형에 정의 된 각 값은 2 개 또는의 조합을 활용 하는 경우에 값을 정의 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 제거 <xref:System.FlagsAttribute> 열거형에서입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca2217.api_surface = private, internal
```

이 범주 (사용량)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="examples"></a>예제

다음 코드에서는 열거형 `Color`, 3 값이 들어 있는입니다. 3 개 정의 된 값의 조합을 활용 아닙니다. 합니다 `Color` 열거형으로 표시 해서는 안 됩니다 <xref:System.FlagsAttribute>합니다.

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

다음 코드는 열거형을 보여 줍니다 `Days`를 사용 하 여 표시 하는 것에 대 한 요구 사항을 충족 하는 <xref:System.FlagsAttribute>:

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>관련된 규칙

[CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.FlagsAttribute?displayProperty=fullName>
