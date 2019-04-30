---
title: 'CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32ac2e430abdc068070457dcf362e39dcbc0b398
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797550"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

두 형식, 멤버, 매개 변수 또는 정규화 된 네임 스페이스의 이름을 소문자로 변환 하는 경우 동일 합니다.

기본적으로이 규칙만 외부에서 표시 되는 형식, 멤버 및 네임 스페이스에서 보이지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다. 예를 들어 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 은 널리 사용 되는 대/소문자 언어입니다.

이 규칙은 공개적으로 표시 하는 멤버에만 실행 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

대/소문자 구분 방식으로 다른 식별자를 비교 했을 때 고유 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다. 라이브러리는.NET Framework에서 사용 가능한 모든 언어에서 사용 하지 못할 수 있습니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1708.api_surface = private, internal
```

이 범주 (이름 지정)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example-of-a-violation"></a>위반의 예

다음 예제에서는이 규칙 위반을 보여 줍니다.

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)