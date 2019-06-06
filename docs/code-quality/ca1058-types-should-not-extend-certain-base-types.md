---
title: 'CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4157316756e4b180f6fb49082bf60927ddb43707
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714800"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식 기본 형식 중 하나를 확장 합니다.

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

기본적으로이 규칙만 살펴봅니다 형식 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

예외에서 파생 되어야 <xref:System.Exception?displayProperty=fullName> 또는 해당 하위 클래스 중 하나는 <xref:System> 네임 스페이스입니다.

서브 클래스를 만들지 마십시오 <xref:System.Xml.XmlDocument> 기본 개체 모델 또는 데이터 원본 XML 뷰를 만들려는 경우입니다.

### <a name="non-generic-collections"></a>제네릭이 아닌 컬렉션

사용 하거나 가능한 제네릭 컬렉션을 확장 합니다. 이전에 제공한 경우가 아니면 코드에서 제네릭이 아닌 컬렉션을 확장 되지 않습니다.

**잘못 된 사용의 예**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**올바른 사용법의 예**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 형식을 다른 기본 형식 또는 제네릭 컬렉션에서 파생 됩니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

에 대 한 위반에 대 한이 규칙에서 경고를 표시 하지 마십시오 <xref:System.ApplicationException>합니다. 에 대 한 위반에 대 한이 규칙에서 경고를 표시 하지 않아도 안전 합니다 <xref:System.Xml.XmlDocument>합니다. 코드를 이전에 릴리스된 경우 제네릭이 아닌 컬렉션에 대 한 경고를 표시 하지 않으려면 안전 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1058.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.