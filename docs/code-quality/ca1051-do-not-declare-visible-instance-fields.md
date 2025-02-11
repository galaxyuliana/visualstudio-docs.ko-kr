---
title: 'CA1051: 표시되는 인스턴스 필드를 선언하지 마세요.'
ms.date: 03/11/2019
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
ms.openlocfilehash: c5dd8a4b2d0b32a8c52f75dee6fd765a7ea6ec9a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547562"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: 표시되는 인스턴스 필드를 선언하지 마세요.

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식에 전용이 아닌 인스턴스 필드가 있습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

필드의 주된 용도는 구현을 세부적으로 설명하는 것입니다. 필드는 또는 `private` `internal` 여야 하 고 속성을 사용 하 여 노출 되어야 합니다. 필드에 액세스 하는 것과 같이 속성에 쉽게 액세스할 수 있으며, 형식의 기능이 주요 변경 사항을 도입 하지 않고 확장 될 때 속성의 접근자에 있는 코드가 변경 될 수 있습니다. 전용 또는 내부 필드의 값을 반환 하는 속성은 필드 액세스와 동일 하 게 수행 하도록 최적화 되어 있습니다. 속성에 대해 외부적으로 표시 되는 필드의 사용과 관련 하 여 성능 향상이 거의 없습니다.

외부적으로 표시 되 `public`는 `protected`는, `protected internal` ,`Public` `Protected`및(Visual Basic) 액세스 가능성 수준 에서,및를나타냅니다.`Protected Friend`

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 필드 `private` 를 설정 하거나 `internal` 외부에서 볼 수 있는 속성을 사용 하 여 노출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 외부적으로 표시 되는 필드는 속성에 사용할 수 없는 이점을 제공 하지 않습니다. 또한 public 필드는 [링크 요청](/dotnet/framework/misc/link-demands)으로 보호할 수 없습니다. CA2112 [를 참조 하세요. 보안 형식은 필드](../code-quality/ca2112-secured-types-should-not-expose-fields.md)를 노출 하면 안 됩니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1051.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는이 규칙을 위반`BadPublicInstanceFields`하는 형식 ()을 보여 줍니다. `GoodPublicInstanceFields`수정 된 코드를 표시 합니다.

[!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA2112: 보안 형식은 필드를 노출 하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>참고자료

- [링크 요청](/dotnet/framework/misc/link-demands)