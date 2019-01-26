---
title: 'CA1051: 표시되는 인스턴스 필드를 선언하지 마세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56e5c8f0a0e703bfa2a2cc2419d1bd3be0b0f23a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54917227"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: 표시되는 인스턴스 필드를 선언하지 마세요.

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에 표시 되는 형식에는 외부에서 표시 되는 인스턴스 필드가 있습니다.

## <a name="rule-description"></a>규칙 설명
 필드의 주된 용도는 구현을 세부적으로 설명하는 것입니다. 필드 여야 `private` 또는 `internal` 및 속성을 사용 하 여 노출 되어야 합니다. 같은 필드에 액세스 하는 것이 고 형식 기능의 주요 변경 내용 없이 확장 속성의 접근자에서 코드를 변경할 수 속성에 액세스 하는 것이 쉽습니다. 만 전용 또는 내부 필드의 값을 반환 하는 속성 필드를 액세스와 일치 하는 데 최적화 되어 속성에 대해 거의 성능이 외부적으로 표시 되는 필드의 사용과 관련이 있습니다.

 외부에서 볼 수 가리킵니다 `public`, `protected`, 및 `protected internal` (`Public`를 `Protected`, 및 `Protected Friend` Visual Basic에서) 액세스 가능성 수준입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 필드 `private` 또는 `internal` 외부에서 볼 수 있는 속성을 사용 하 여 노출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다. 외부에서 표시 되는 필드 속성을 사용할 수 없는 모든 혜택을 제공 하지 않습니다. 또한으로 public 필드를 보호할 수 없습니다 [링크 요구가](/dotnet/framework/misc/link-demands)합니다. 참조 [CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식을 보여 줍니다 (`BadPublicInstanceFields`)는이 규칙을 위반 합니다. `GoodPublicInstanceFields` 수정 된 코드를 보여 줍니다.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>참고자료
 [링크 요청](/dotnet/framework/misc/link-demands)