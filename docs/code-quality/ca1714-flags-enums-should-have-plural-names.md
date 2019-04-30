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
ms.openlocfilehash: f5a1532b67fdaeb2a44663db77cfc8a1056004e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546175"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

열거형에는 <xref:System.FlagsAttribute?displayProperty=fullName> 이름과 끝나지 및에서 '.

기본적으로이 규칙만 살펴봅니다 열거형 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

형식으로 표시 된 <xref:System.FlagsAttribute> 둘 이상의 값을 지정할 수 있음을 나타내므로 특성에는 복수형 이름을 갖습니다. 예를 들어 일 주를 정의 하는 열거형 수 사용 하려는 응용 프로그램에서 여러 날짜를 지정할 수 있습니다. 이 열거형 있어야는 <xref:System.FlagsAttribute> '일' 호출할 수 없습니다. 하루를 지정할 수 있도록 유사한 열거형은 특성 없고 수 'Day'를 호출 합니다.

명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

열거형의 이름을 복수 단어를 만들거나 제거 합니다 <xref:System.FlagsAttribute> 특성 여러 열거 값을 동시에 지정 되지 않아야 하는 경우.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이름이 복수형 단어 이지만 끝나지 위반을 보류 하려면 안전의 '. 예를 들어, 이전에 설명 된 여러 날짜 열거형 'DaysOfTheWeek' 이름이 지정 된,이 규칙이 있지만 의도 하지 논리를 위반 것입니다. 이러한 위반 되지 않아야 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1714.api_surface = private, internal
```

이 범주 (이름 지정)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [열거형 디자인](/dotnet/standard/design-guidelines/enum)