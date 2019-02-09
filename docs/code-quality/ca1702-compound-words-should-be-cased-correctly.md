---
title: 'CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다.'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f78ea4f44c48d2740df58def03a6335bce6637a2
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55942767"
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다.

|||
|-|-|
|TypeName|CompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1702|
|범주|Microsoft.Naming|
|변경 수준|어셈블리에 주요-경우에 발생합니다.<br /><br /> 주요 변경 아님-형식 매개 변수에서 발생 한 경우|

## <a name="cause"></a>원인

식별자 이름에 여러 개의 단어가 포함되어 있으며 이 중 적어도 하나의 단어가 대/소문자를 정확하게 사용하지 않은 복합 단어인 것 같습니다.

## <a name="rule-description"></a>규칙 설명

이름 식별자의 대/소문자를 기반으로 하는 단어로 분할 됩니다. 각 연속 된 두 단어 조합에 Microsoft 맞춤법 검사 라이브러리에서 확인 됩니다. 인식 되는 식별자 규칙 위반을 생성 합니다. 위반이 발생 하는 복합 단어의 예로 "CheckSum" 및 "MultiPart"는 대/소문자 "Checksum" 및 "Multipart"로 각각를 들 수 있습니다. 이전 일반적인 사용량으로 인해 몇 가지 예외는 규칙에 기본 제공 되며 여러 단어에 플래그가 지정 됩니다 "Toolbar" 및 "Filename"와 같은 표기 해야 (이 경우 "ToolBar" 및 "FileName")의 두 고유 단어입니다.

명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

올바르게 소문자를 사용 하므로 이름을 변경 합니다.

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

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

복합 단어의 두 파트 맞춤법 사전에서 인식 되 고 두 단어를 사용 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙

- [CA1701: 리소스 문자열 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>참고자료

- [명명 지침](/dotnet/standard/design-guidelines/naming-guidelines)
- [대/소문자 표기법](/dotnet/standard/design-guidelines/capitalization-conventions)