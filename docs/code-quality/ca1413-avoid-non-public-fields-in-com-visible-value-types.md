---
title: 'CA1413: COM 노출 값 형식에 public이 아닌 필드를 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3eb216af1b6cd742aff83b248b6752adea292345
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921834"
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: COM 노출 값 형식에 public이 아닌 필드를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|
|CheckId|CA1413|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
COM (구성 요소 개체 모델)에 표시 되도록 특별히 표시 되는 값 형식은 public이 아닌 인스턴스 필드를 선언 합니다.

## <a name="rule-description"></a>규칙 설명
public이 아니며 값 형식이 COM에 노출되는 인스턴스 필드는 COM 클라이언트에서 볼 수 있습니다. 필드의 내용을 검토 하 여 노출 되지 않아야 하거나 의도 하지 않은 디자인 또는 보안 효과가 적용 되는 정보를 검토 합니다.

기본적으로 모든 공용 값 형식은 COM에 표시 됩니다. 그러나 가양성을 줄이기 위해이 규칙을 사용 하려면 형식에 대 한 COM 표시 유형을 명시적으로 명시 해야 합니다. 포함 하 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 는 어셈블리는로 `false` 설정 된로 표시 되어야 하 고 형식은로 <xref:System.Runtime.InteropServices.ComVisibleAttribute> `true`설정 된로 표시 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하 고 필드를 숨기려면 값 형식을 참조 형식으로 변경 하거나 형식에서 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
필드의 공개 노출을 허용 하는 경우이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
[!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA1407: COM 노출 형식에 정적 멤버를 사용 하지 마십시오.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고자료

- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)
- [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)