---
title: 'CA1041: ObsoleteAttribute 메시지를 제공하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ad693014a7f6c16484f03c2d2f746c8159cf160e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778869"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute 메시지를 제공하세요.

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식 또는 멤버를 사용 하 여 표시 되는 <xref:System.ObsoleteAttribute?displayProperty=fullName> 하지 않은 특성 해당 <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> 지정 된 속성입니다.

기본적으로이 규칙만 살펴봅니다 외부적으로 표시 되는 형식 및 멤버 이지만 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

<xref:System.ObsoleteAttribute> 사용 되지 않는 라이브러리 형식 및 멤버를 표시 하는 데 사용 됩니다. 라이브러리 소비자는 모든 형식 또는 obsolete로 표시 되어 있는 멤버의 사용을 피해 야 합니다. 이 지원 되지 않는 경우 해당 라이브러리의 이후 버전에서 제거 됩니다 때문입니다. 형식 또는 멤버를 사용 하 여 표시 하는 경우 <xref:System.ObsoleteAttribute> 컴파일되면는 <xref:System.ObsoleteAttribute.Message%2A> 특성의 속성이 표시 됩니다. 사용되지 않는 형식 또는 멤버에 대한 정보가 사용자에게 제공됩니다. 라이브러리 디자이너가 정보와 대신 사용 하도록에서 지원 되는 멤버 또는이 정보에는 일반적으로 사용 되지 않는 기간 형식 포함 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 추가 합니다 `message` 매개 변수는 <xref:System.ObsoleteAttribute> 생성자입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

때문에이 규칙에서 경고를 표시 하지 마십시오는 <xref:System.ObsoleteAttribute.Message%2A> 속성은 사용 되지 않는 형식 또는 멤버에 대 한 중요 한 정보를 제공 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1041.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 제대로 선언에 사용 되지 않는 멤버를 <xref:System.ObsoleteAttribute>입니다.

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>참고자료

- <xref:System.ObsoleteAttribute?displayProperty=fullName>