---
title: 'CA2112: 보안 형식은 필드를 노출하면 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 43ef4165823f59045dda8c05b5679fdd3b795114
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921090"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: 보안 형식은 필드를 노출하면 안 됩니다.

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
Public 또는 protected 형식은 public 필드를 포함 하 고 [링크 요청](/dotnet/framework/misc/link-demands)에 의해 보호 됩니다.

## <a name="rule-description"></a>규칙 설명
코드에 링크 요청으로 보안된 형식의 인스턴스에 대한 액세스 권한이 있으면 코드에서 링크 요청을 만족하지 않아도 해당 형식의 필드에 액세스할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 필드를 비공용으로 설정 하 고 필드 데이터를 반환 하는 공용 속성 또는 메서드를 추가 합니다. 형식에 대 한 LinkDemand 보안 검사는 형식의 속성 및 메서드에 대 한 액세스를 보호 합니다. 그러나 코드 액세스 보안은 필드에 적용 되지 않습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
보안 문제 및 좋은 디자인의 경우 모두 public 필드를 public으로 설정 하 여 위반 문제를 해결 해야 합니다. 필드에 보안을 유지 해야 하는 정보가 포함 되어 있지 않고 필드의 내용을 사용 하지 않을 경우이 규칙에서 경고를 표시 하지 않을 수 있습니다.

## <a name="example"></a>예제
다음 예제는 보안 되지 않은 필드가 있는 라이브러리 형식`SecuredTypeWithFields`(), 라이브러리 형식의 인스턴스를 만들`Distributor`수 있는 형식 (), 라이브러리 형식의 인스턴스를 만들 수 있는 형식 () 및 형식에 대 한 인스턴스를 만들 수 있는 권한이 없는 형식 ()으로 구성 되어 있습니다. 응용 프로그램 코드는 는 형식을 보호 하는 사용 권한이 없더라도 인스턴스의 필드를 읽을 수 있습니다.

다음 라이브러리 코드는 규칙을 위반 합니다.

[!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>예제 1
보안 형식을 보호 하는 링크 요청으로 인해 응용 프로그램에서 인스턴스를 만들 수 없습니다. 다음 클래스를 사용 하면 응용 프로그램에서 보안 형식의 인스턴스를 가져올 수 있습니다.

[!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>예제 2
다음 응용 프로그램에서는 보안 형식의 메서드에 액세스할 수 있는 권한이 없는 코드에서 해당 필드에 액세스할 수 있는 방법을 보여 줍니다.

[!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>관련 규칙

- [CA1051: 표시 되는 인스턴스 필드를 선언 하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>참고자료

- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)