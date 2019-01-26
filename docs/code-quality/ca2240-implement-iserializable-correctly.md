---
title: 'CA2240: ISerializable을 올바르게 구현하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1924b86945df73ccd84f1215367d44d9ead039aa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971288"
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: ISerializable을 올바르게 구현하십시오.

|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|CheckId|CA2240|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

외부에 표시 되는 형식은에 할당할 수는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스 및 다음 조건 중 하나가 참인:

- 형식 상속 하지만 재정의 하지 않습니다 합니다 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드 및 형식으로 표시 되지 않는 인스턴스 필드를 선언 합니다 <xref:System.NonSerializedAttribute?displayProperty=fullName> 특성입니다.

- Sealed 형식 인지 및 형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 외부적으로 표시 하 고 재정의 가능 하지 않은 메서드.

## <a name="rule-description"></a>규칙 설명
 상속 된 형식에서 선언 된 필드를 인스턴스는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스 serialization 프로세스에 자동으로 포함 되지 않습니다. 형식 필드를 포함 하려면 구현 해야 합니다는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드와 serialization 생성자입니다. 필드를 직렬화 하지 해야 하는 경우 적용 된 <xref:System.NonSerializedAttribute> 특성 필드를 명시적으로 지정 하는 의사 결정을 합니다.

 구현을 봉인 되지 않은 형식에는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 외부에서 표시 되어야 합니다. 따라서 메서드는 파생된 형식에서 호출할 수 있습니다 하 고 재정의할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 합니다 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 표시 되 고 재정의 가능한 메서드 모든 인스턴스 필드가 serialization 프로세스에 포함 하거나 명시적으로 표시 되었는지 확인 합니다 <xref:System.NonSerializedAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 두 가지 직렬화 형식을 보여 줍니다.

 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]

## <a name="example"></a>예제
 다음 예제에서는 재정의 가능한 구현을 제공 하 여 두 개의 이전 위반 수정 <xref:System.Runtime.Serialization.ISerializable.GetObjectData> Book 클래스에 구현을 제공 하 여 `GetObjectData` 라이브러리 클래스에 있습니다.

 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]

## <a name="related-rules"></a>관련된 규칙

- [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 합니다.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2235: 모든 순차 불가능 필드를 표시 합니다.](../code-quality/ca2235-mark-all-non-serializable-fields.md)
- [CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2239: 선택적 필드에 deserialization 메서드를 제공 합니다.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)