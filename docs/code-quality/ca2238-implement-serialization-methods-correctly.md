---
title: 'CA2238: serialization 메서드를 올바르게 구현하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
helpviewer_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ec40eb3317f541bec92f06d8921fc2f545606d1a
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920081"
---
# <a name="ca2238-implement-serialization-methods-correctly"></a>CA2238: serialization 메서드를 올바르게 구현하십시오.

|||
|-|-|
|TypeName|ImplementSerializationMethodsCorrectly|
|CheckId|CA2238|
|범주|Microsoft.Usage|
|변경 수준|중단-메서드가 어셈블리 외부에 표시 되는 경우입니다.<br /><br /> 분리 안 함-메서드가 어셈블리 외부에 표시 되지 않는 경우|

## <a name="cause"></a>원인
serialization 이벤트를 처리하는 메서드에 올바른 시그니처, 반환 형식 또는 노출 수준이 없습니다.

## <a name="rule-description"></a>규칙 설명
메서드는 다음 직렬화 이벤트 특성 중 하나를 적용 하 여 serialization 이벤트 처리기로 지정 됩니다.

- <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>

  Serialization 이벤트 처리기는 형식의 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>단일 매개 변수를 사용 하 고를 반환 `private` `void`하며 표시 유형을 갖습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 serialization 이벤트 처리기의 서명, 반환 형식 또는 표시 유형을 수정 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 올바르게 선언 된 serialization 이벤트 처리기를 보여 줍니다.

[!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
[!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 합니다.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

[CA2240: ISerializable을 올바르게 구현 하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2239: 선택적 필드에 deserialization 메서드 제공](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)