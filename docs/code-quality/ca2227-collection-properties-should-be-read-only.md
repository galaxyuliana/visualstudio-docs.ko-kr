---
title: 'CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.'
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 8a6ced277aa442450418ce55f4e1db56ad5d8af1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806539"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|범주|Microsoft.Usage|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

구현 하는 형식 외부에 표시 되는 쓰기 가능한 속성은 <xref:System.Collections.ICollection?displayProperty=fullName>합니다. 이 규칙은 배열, 인덱서 ('Item' 이름의 속성) 및 권한 집합을 무시합니다.

## <a name="rule-description"></a>규칙 설명

쓰기 가능한 컬렉션 속성을 사용 하면 완전히 다른 컬렉션으로 바꿀 수 있습니다. 읽기 전용 속성을 바꾸지 못하도록 수집을 중지 하지만 여전히 개별 멤버를 설정할 수 있습니다. 컬렉션을 대체 하는 것은 목표를 선호 하는 설계 패턴 경우 컬렉션에서 모든 요소를 제거 하는 메서드 및 컬렉션을 다시 채워야 하는 메서드를 포함 합니다. 참조를 <xref:System.Collections.ArrayList.Clear%2A> 하 고 <xref:System.Collections.ArrayList.AddRange%2A> 의 메서드는 <xref:System.Collections.ArrayList?displayProperty=fullName> 이 패턴의 예는 클래스입니다.

이진 및 XML serialization은 읽기 전용 속성을 지원 합니다. 합니다 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 클래스에 구현 하는 형식에 대 한 특정 요구 사항이 <xref:System.Collections.ICollection> 및 <xref:System.Collections.IEnumerable?displayProperty=fullName> 직렬화가 가능 하기 위해.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 읽기 전용 속성을 확인 합니다. 디자인에 필요한 경우 선택을 취소 하 고 컬렉션을 다시 채우는 메서드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

속성의 일부인 경우 경고를 표시 하지 않을 수는 [데이터 전송 개체 (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) 클래스입니다.

그렇지 않은 경우이 규칙에서 경고를 표시 하지 마십시오.

## <a name="example"></a>예제

다음 예에서는 쓰기 가능한 컬렉션 속성을 사용 하 여 형식을 보여 줍니다 및 컬렉션을 직접 바꿀 수 있습니다 하는 방법을 보여 줍니다. 또한 사용 하 여 읽기 전용 컬렉션 속성을 바꾸는 방법도 보여 줍니다 `Clear` 고 `AddRange` 메서드.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>관련된 규칙

- [CA1819: 속성은 배열을 반환 해서는](../code-quality/ca1819-properties-should-not-return-arrays.md)