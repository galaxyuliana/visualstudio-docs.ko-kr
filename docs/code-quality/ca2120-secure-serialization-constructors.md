---
title: 'CA2120: serialization 생성자를 안전하게 하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dc7f4a82b9a75e4d189e969712472f06b4019b73
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920874"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: serialization 생성자를 안전하게 하세요.

|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
형식은 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현 하 고, 대리자 또는 인터페이스가 아니고, 부분적으로 신뢰할 수 있는 호출자를 허용 하는 어셈블리에서 선언 됩니다. 형식에는 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> 개체 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 와 개체 (serialization 생성자의 시그니처)를 사용 하는 생성자가 있습니다. 이 생성자는 보안 검사를 통해 보안 되지 않지만 형식에 있는 하나 이상의 일반 생성자가 보안 됩니다.

## <a name="rule-description"></a>규칙 설명
이 규칙은 사용자 지정 serialization을 지 원하는 형식과 관련이 있습니다. 인터페이스를 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 구현 하는 경우 형식이 사용자 지정 serialization을 지원 합니다. Serialization 생성자는 필수 이며 메서드를 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 사용 하 여 serialize 된 개체를 역직렬화 하거나 다시 만드는 데 사용 됩니다. Serialization 생성자는 개체를 할당 하 고 초기화 하므로, 일반 생성자에 있는 보안 검사도 serialization 생성자에 있어야 합니다. 이 규칙을 위반 하는 경우 인스턴스를 만들 수 없는 호출자는 serialization 생성자를 사용 하 여이 작업을 수행할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 다른 생성자를 보호 하는 것과 동일한 보안 요구 사항을 사용 하 여 serialization 생성자를 보호 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
규칙 위반을 억제 하지 마십시오.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

[!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>