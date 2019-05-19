---
title: 'CA1720: 식별자에 형식 이름을 포함하면 안 됩니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c596ddfa36beec696c275ea13b662ceebf8bde2c
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841789"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: 식별자에 형식 이름을 포함하면 안 됩니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

데이터 형식 이름을 포함 하는 멤버의 매개 변수 이름입니다.

또는

언어 특정 데이터 형식 이름을 포함 하는 멤버의 이름입니다.

기본적으로이 규칙만 외부에서 볼 수 멤버 보이지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

매개 변수 및 멤버의 이름과 설명, 개발 도구에 의해 제공 될 예상 되는 형식 보다는 의미를 전달할 잘 사용 됩니다. 멤버 이름에 대 한 데이터 형식 이름을 사용 해야 하는 경우 언어별 단일 대신 언어 독립적인 이름을 사용 합니다. Of 예를 들어는 C# 형식 이름 `int`, 언어 독립적인 데이터 형식 이름을 사용 하 여 `Int32`합니다.

각 개별 토큰 매개 변수 또는 멤버의 이름을 다음 언어 특정 데이터 형식 이름에 대해 대/소문자 구분 방식으로 확인 됩니다.

- Bool
- WChar
- Int8
- UInt8
- Short
- UShort
- Int
- UInt
- 정수
- UInteger
- Long
- ULong
- 부호 없음
- 서명
- Float
- Float32
- Float64

또한 매개 변수의 이름은 확인 됩니다 다음 언어에 관계 없이 데이터 형식 이름에 대해 대/소문자 구분 방식.

- 개체
- obj
- Boolean
- Char
- 문자열
- SByte
- Byte
- UByte
- Int16
- UInt16
- Int32
- UInt32
- Int64
- UInt64
- IntPtr
- ptr
- 포인터
- UInptr
- UPtr
- UPointer
- Single
- Double
- Decimal
- Guid

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

**매개 변수에서 발생 한 경우:**

데이터 형식 식별자를 매개 변수 이름을 더 의미를 설명 하는 용어 또는 'value'와 같은 보다 일반적인 용어를 바꿉니다.

**발생 한 경우 멤버에 대해:**

해당 의미, 언어에 관계 없이 해당 하는, 'value'와 같은 보다 일반적인 용어를 더 잘 설명 하는 용어를 사용 하 여 멤버 이름의 언어 특정 데이터 형식 식별자를 대체 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

형식 기반 매개 변수 및 멤버 이름의 가끔 사용 적절할 수 있습니다. 그러나 새로운 개발에 알려져 있지 않습니다에 대 한 시나리오 발생이 규칙에서 경고를 표시 해야 하는 위치입니다. 에 이전에 제공 된 라이브러리에 대 한이 규칙에서 경고를 표시 해야 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1720.api_surface = private, internal
```

이 범주 (이름 지정)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707: 식별자에는 밑줄 없어야 합니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1719: 매개 변수 이름은 멤버 이름과 일치 하지는](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)