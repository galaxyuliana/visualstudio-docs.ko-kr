---
title: 'CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d71200c6c7fbb61e7994119fde5e75f7623fa669
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547196"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

열거형에가 <xref:System.FlagsAttribute?displayProperty=fullName> 있고 해당 이름이의 ' '로 끝나지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 열거만 보이지만 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

로 <xref:System.FlagsAttribute> 표시 된 형식에는 두 개 이상의 값을 지정할 수 있음을 나타내는 특성으로 인해 복수형 이름이 있습니다. 예를 들어 요일을 정의 하는 열거형은 여러 날짜를 지정할 수 있는 응용 프로그램에서 사용 하기 위한 것입니다. 이 열거형에는를 <xref:System.FlagsAttribute> 포함 해야 하며 ' 일 '을 호출할 수 있습니다. 하루에 한 번만 지정할 수 있는 유사한 열거형은 특성이 없으며 ' Day '를 호출할 수 있습니다.

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요한 학습 곡선이 줄어들고, 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 했을 때 고객의 자신감을 높일 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

열거형의 이름을 복수 단어로 설정 하거나 여러 열거형 값을 동시에 <xref:System.FlagsAttribute> 지정 하지 않아야 하는 경우 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이름이 복수형 인 경우에는 '. '로 끝나지 않는 경우 위반을 무시 해도 됩니다. 예를 들어 앞에서 설명한 여러 날 열거의 이름이 ' DaysOfTheWeek ' 인 경우이는 규칙의 논리를 위반 하지만 의도는 위반 하지 않습니다. 이러한 위반은 무시 해야 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1714.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="related-rules"></a>관련 규칙

- [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: 열거형을 FlagsAttribute로 표시 하지 않습니다.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [열거형 디자인](/dotnet/standard/design-guidelines/enum)