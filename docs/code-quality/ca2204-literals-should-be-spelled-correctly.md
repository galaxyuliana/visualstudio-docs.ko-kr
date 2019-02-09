---
title: 'CA2204: 리터럴의 맞춤법이 정확해야 합니다.'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82146c2ac997a0202c20e15492becb89a293f427
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949449"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: 리터럴의 맞춤법이 정확해야 합니다.

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

리터럴 문자열을 지역화할 수 있는 매개 변수 또는 지역화할 수 있는 속성에 인수로 전달 됩니다 및 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식 하지 못하는 단어가 하나 이상 포함 되어 있습니다.

## <a name="rule-description"></a>규칙 설명

매개 변수 또는 경우에 속성 값으로 전달 되는 리터럴 문자열을 검사 하는이 규칙 또는 다음 경우 중 더 그렇습니다.

- <xref:System.ComponentModel.LocalizableAttribute> 매개 변수 또는 속성의 특성은 설정을 true로 합니다.

- "Text", "Message" 또는 "캡션"를 포함 하는 매개 변수 또는 속성 이름입니다.

- 에 전달 되는 문자열 변수의 이름을 <xref:System.Console.Write%2A> 또는 <xref:System.Console.WriteLine> 메서드는 "value" 또는 "format"입니다.

이 규칙 복합 단어를 토큰화 리터럴 문자열을 구문 분석 하 고 각 단어 또는 토큰의 맞춤법을 검사 합니다. 구문 분석 알고리즘에 대 한 자세한 내용은 [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)합니다.

## <a name="language"></a>언어

맞춤법 검사기는 현재 영어 기반 문화권 사전에 대해서만 확인합니다. 추가 하 여 프로젝트 파일에서 프로젝트의 문화권을 변경할 수 있습니다 합니다 **CodeAnalysisCulture** 요소입니다.

예를 들어:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> 문화권을 영어 기반 문화권 이외의 값으로 설정한 경우이 코드 분석 규칙은 자동으로 비활성화 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 단어의 철자를 수정 하거나 사용자 지정 사전에 단어를 추가 합니다. 사용자 지정 사전을 사용 하는 방법에 대 한 정보를 참조 하세요. [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다. 올바르게 맞춤법이 단어는 새 소프트웨어 라이브러리에 필요한 학습 곡선을 줄어듭니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA1703: 리소스 문자열에는 정확한 철자를 사용 해야](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)