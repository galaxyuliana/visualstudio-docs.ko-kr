---
title: 'CA2239: 선택적 필드에 deserialization 메서드를 제공하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c0cd59ec30ce45c94ac3422c4271959d74073bff
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920058"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239: 선택적 필드에 deserialization 메서드를 제공하세요.

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
형식에는 <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> 특성으로 표시 되는 필드가 있으며,이 형식은 역직렬화 이벤트 처리 메서드를 제공 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
특성 <xref:System.Runtime.Serialization.OptionalFieldAttribute> 은 serialization에 영향을 주지 않습니다. 특성으로 표시 된 필드는 serialize 됩니다. 그러나 역직렬화에서 필드는 무시 되 고 해당 형식과 연결 된 기본값을 유지 합니다. 직렬화 해제 프로세스 중에 필드를 설정 하려면 역직렬화 이벤트 처리기를 선언 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 역직렬화 이벤트 처리 메서드를 형식에 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
Serialization 프로세스 중에 필드를 무시 해야 하는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 선택적 필드 및 역직렬화 이벤트 처리 메서드를 사용 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
[!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]

## <a name="related-rules"></a>관련 규칙
[CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 합니다.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

[CA2240: ISerializable을 올바르게 구현 하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)