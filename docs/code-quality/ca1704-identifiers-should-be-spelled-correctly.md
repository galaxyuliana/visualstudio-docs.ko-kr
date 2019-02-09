---
title: 'CA1704: 식별자에는 정확한 철자를 사용해야 합니다.'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8dbfc8081f980b7b9e978da782f1627a88a716a3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55941286"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: 식별자에는 정확한 철자를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

Microsoft 맞춤법 검사 라이브러리에서 인식 하지 못하는 단어가 하나 이상 포함 하는 식별자의 이름입니다. 이 규칙 생성자 또는 get 같은 특수 한 이름의 멤버를 확인 하지 않으며 속성 접근자를 설정 합니다.

## <a name="rule-description"></a>규칙 설명

이 규칙의 식별자를 토큰으로 구문 분석 및 각 토큰의 맞춤법을 검사 합니다. 구문 분석 알고리즘은 다음과 같은 변환을 수행합니다.

- 대문자는 새 토큰을 시작 합니다. 예를 들어 "My", "Name", "Is", "Joe" MyNameIsJoe 토큰화 합니다.

- 여러 대문자에 대 한 마지막 대문자 새 토큰을 시작합니다. 예를 들어 GUIEditor "GUI", "편집기"를 토큰화 합니다.

- 선행 및 후행 아포스트로피 제거 됩니다. 예를 들어 "보낸 사람에 게" 'sender' 토큰화 합니다.

- 밑줄 토큰의 끝을 나타냅니다 하 고 제거 됩니다. Hello_world "Hello"를 토큰화 하는 예를 들어, "world"입니다.

- 포함 된 앰퍼샌드 제거 됩니다. 예를 들어 for&mat은 "format"으로 토큰화됩니다.

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

이 규칙 위반 문제를 해결 하는 단어의 철자를 수정 하거나 사용자 지정 사전에 단어를 추가 합니다.

### <a name="to-add-words-to-a-custom-dictionary"></a>사용자 지정 사전에 단어를 추가 하려면

사용자 지정 사전을 XML 파일의 이름을 *CustomDictionary.xml*합니다. 사용자의 프로필 아래에 있는 도구를 사용 하 여 연결 된 디렉터리 또는 도구를 프로젝트 디렉터리의 설치 디렉터리에서 사전 배치 (*%USERPROFILE%\Application 데이터\\...* ). Visual Studio에서 프로젝트에 사용자 지정 사전을 추가 하는 방법에 알아보려면 참조 [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)합니다.

- 사전/단어/인식 경로의 위반을 발생 시킵니다 해야 하는 단어를 추가 합니다.

- 인식할 수 없음 사전/단어/경로 아래에서 위반이 발생 해야 하는 단어를 추가 합니다.

- 사전/단어/사용 되지 않는 경로 아래에서 사용 되지 않는 플래그를 지정 해야 하는 단어를 추가 합니다. 관련된 규칙 항목을 참조 [CA1726: 기본 설정된 용어를 사용 하 여](../code-quality/ca1726-use-preferred-terms.md) 자세한 내용은 합니다.

- 사전/머리 글자어/CasingExceptions 경로로 머리글자어 대/소문자 규칙에 예외를 추가 합니다.

다음은 사용자 지정 사전 파일 구조의 예제입니다.

```xml
<Dictionary>
   <Words>
      <Unrecognized>
         <Word>cb</Word>
      </Unrecognized>
      <Recognized>
         <Word>stylesheet</Word>
         <Word>GotDotNet</Word>
      </Recognized>
      <Deprecated>
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>
      </Deprecated>
   </Words>
   <Acronyms>
      <CasingExceptions>
         <Acronym>CJK</Acronym>
         <Acronym>Pi</Acronym>
      </CasingExceptions>
   </Acronyms>
</Dictionary>
```

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

단어는 의도적으로 맞춤법이 틀린 단어 라이브러리의 제한 된 집합을 적용할 경우에이 규칙에서 경고를 표시 합니다. 올바르게 맞춤법이 단어는 새 소프트웨어 라이브러리에 필요한 학습 곡선을 줄어듭니다.

## <a name="related-rules"></a>관련된 규칙

- [CA2204: 리터럴 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703: 리소스 문자열에는 정확한 철자를 사용 해야](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707: 식별자에는 밑줄 없어야 합니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726: 기본 설정된 용어를 사용 합니다.](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>참고자료

- [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
