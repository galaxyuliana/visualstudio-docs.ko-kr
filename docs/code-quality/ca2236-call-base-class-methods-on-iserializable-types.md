---
title: 'CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3f0075a6296e839030448c0209c77f1717a5fcb1
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920127"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
형식은 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현 하는 형식에서 파생 되 고 다음 조건 중 하나에 해당 합니다.

- 형식은 serialization 생성자, 즉 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 매개 변수 시그니처를 사용 하는 생성자를 구현 하지만 기본 형식의 serialization 생성자를 호출 하지 않습니다.

- 형식은 메서드를 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 구현 하지만 기본 형식의 메서드를 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 호출 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
사용자 지정 serialization 프로세스에서 형식은 메서드를 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 구현 하 여 해당 필드를 serialize 하 고 serialization 생성자를 구현 하 여 필드를 역직렬화 합니다. 형식이 인터페이스 <xref:System.Runtime.Serialization.ISerializable> <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 를 구현 하는 형식에서 파생 된 경우 기본 형식 메서드 및 serialization 생성자를 호출 하 여 기본 형식의 필드를 직렬화/역직렬화 해야 합니다. 그렇지 않으면 형식이 serialize 되지 않고 올바르게 serialize 되지 않습니다. 파생 형식이 새 필드를 추가 하지 않으면 형식이 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 또는 serialization 생성자를 구현 하거나 해당 하는 기본 형식을 호출할 필요가 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 해당 파생 형식 메서드나 생성자 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 에서 기본 형식 메서드 또는 serialization 생성자를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 기본 클래스의 serialization 생성자와 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드를 호출 하 여 규칙을 충족 하는 파생 형식을 보여 줍니다.

[!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
[!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA2240: ISerializable을 올바르게 구현 하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2239: 선택적 필드에 deserialization 메서드 제공](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

[CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)