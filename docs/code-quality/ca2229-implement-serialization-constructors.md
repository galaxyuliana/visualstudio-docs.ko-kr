---
title: 'CA2229: serialization 생성자를 구현하십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11dfa98bb348f874a2774454cc465fb80cb71750
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920158"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: serialization 생성자를 구현하십시오.

|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
형식은 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현 하 고, 대리자 또는 인터페이스가 아니고, 다음 조건 중 하나에 해당 합니다.

- 형식에 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> 개체 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 와 개체 (serialization 생성자의 시그니처)를 사용 하는 생성자가 없습니다.

- 형식이 봉인 되지 않고 serialization 생성자의 액세스 한정자가 (family) 보호 되지 않습니다.

- 형식이 sealed이 고 serialization 생성자의 액세스 한정자가 private이 아닙니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 사용자 지정 serialization을 지 원하는 형식과 관련이 있습니다. 인터페이스를 <xref:System.Runtime.Serialization.ISerializable> 구현 하는 경우 형식이 사용자 지정 serialization을 지원 합니다. <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드를 사용 하 여 serialize 된 개체를 deserialize 하거나 다시 만들려면 serialization 생성자를 사용 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다. 봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
규칙 위반을 억제 하지 마십시오. 형식은 deserialize 할 수 없으며 여러 시나리오에서 작동 하지 않습니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 충족 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>