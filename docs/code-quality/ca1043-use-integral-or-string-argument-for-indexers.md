---
title: 'CA1043: 인덱서에 정수 또는 문자열 인수를 사용하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: aeec6e202ccb7f3075b04d29bdef7d171ae545f7
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547691"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: 인덱서에 정수 또는 문자열 인수를 사용하세요.

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

<xref:System.Int32?displayProperty=fullName> ,<xref:System.Int64?displayProperty=fullName>, 또는 이외의<xref:System.String?displayProperty=fullName>인덱스 유형을 사용 하는 인덱서가 형식에 포함 되어 있습니다. <xref:System.Object?displayProperty=fullName>

기본적으로이 규칙은 공용 및 보호 된 형식만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

인덱싱된 속성인 인덱서는 인덱스에 정수 또는 문자열 형식을 사용 해야 합니다. 이러한 형식은 일반적으로 데이터 구조를 인덱싱하는 데 사용 되며 라이브러리의 유용성을 향상 시킵니다. 디자인 타임에 <xref:System.Object> 특정 정수 또는 문자열 형식을 지정할 수 없는 경우에는 형식의 사용을 제한 해야 합니다. 디자인에서 인덱스에 다른 형식이 필요한 경우 형식이 논리적 데이터 저장소를 나타내는지 여부를 고려해 야 합니다. 논리적 데이터 저장소를 나타내지 않는 경우 메서드를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 인덱스를 정수 또는 문자열 형식으로 변경 하거나 인덱서 대신 메서드를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에만이 규칙에서 경고를 표시 하지 않습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1043.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 <xref:System.Int32> 인덱스를 사용 하는 인덱서를 보여 줍니다.

[!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
[!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
[!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>관련 규칙

- [CA1023: 인덱서는 다차원 일 수 없습니다.](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)
- [CA1024: 적절 한 경우 속성 사용](../code-quality/ca1024-use-properties-where-appropriate.md)