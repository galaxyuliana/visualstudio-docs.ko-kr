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
ms.openlocfilehash: 5098e2feadc6d67c466e31ab19d059ac70c7d833
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547403"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

두 형식, 멤버, 매개 변수 또는 정규화 된 네임 스페이스의 이름은 소문자로 변환할 때 동일 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식, 멤버 및 네임 스페이스도 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다. 예를 들어 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 는 널리 사용 되는 대/소문자를 구분 하지 않는 언어입니다.

이 규칙은 공개적으로 표시 되는 멤버에 대해서만 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

대/소문자를 구분 하지 않는 방식으로 다른 식별자와 비교할 때 고유한 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 이 라이브러리는 .NET에서 사용 가능한 모든 언어에서 사용할 수 없습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1708.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example-of-a-violation"></a>위반 예

다음 예제에서는이 규칙을 위반 하는 방법을 보여 줍니다.

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1709: 식별자의 대/소문자를 올바르게 지정 해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)