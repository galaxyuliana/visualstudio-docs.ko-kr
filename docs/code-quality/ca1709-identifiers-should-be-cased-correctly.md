---
title: 'CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IdentifiersShouldBeCasedCorrectly
- CA1709
helpviewer_keywords:
- CA1709
- IdentifiersShouldBeCasedCorrectly
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 864918b7ce394e9f096c6fa9dea9389957983177
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921771"
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldBeCasedCorrectly|
|CheckId|CA1709|
|범주|Microsoft.Naming|
|변경 수준|중단-어셈블리, 네임 스페이스, 형식, 멤버 및 매개 변수에 대해 발생 합니다.<br /><br /> 일반 형식 매개 변수에 대해 발생 하는 경우에는 중단 되지 않습니다.|

## <a name="cause"></a>원인

식별자의 이름은 대/소문자를 올바르게 따르지 않습니다.

\- 또는 -

식별자 이름은 두 문자로 된 머리글자어를 포함 하 고 두 번째 문자는 소문자입니다.

\- 또는 -

식별자 이름에는 3 개 이상의 대문자로 된 머리글자어가 포함 됩니다.

## <a name="rule-description"></a>규칙 설명

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이러한 일관성은 새로운 소프트웨어 라이브러리에 필요한 학습 곡선을 줄이고 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 했다는 확신을 높입니다.

규칙에 따라 매개 변수 이름에 카멜식 대/소문자를 사용 하 고 네임 스페이스, 형식 및 멤버 이름을 파스칼식 대/소문자를 사용 합니다. 카멜식 대/소문자를 구분 하는 이름에서 첫 번째 문자는 소문자 이며 이름에서 나머지 단어의 첫 문자는 대문자입니다. 카멜식 대/소문자를 구분 하 `packetSniffer`는 `ioFile`이름의 예 `fatalErrorCode`는, 및입니다. 파스칼식 대/소문자를 구분 하는 이름에서 첫 문자는 대문자 이며, 이름에서 나머지 단어의 첫 글자는 대문자입니다. 파스칼식 대/소문자 이름 예는 `PacketSniffer`, `IOFile`및 `FatalErrorCode`입니다.

이 규칙은 대/소문자에 따라 이름을 단어로 분할 하 고 두 문자로 된 단어를 "In" 또는 "My"와 같은 일반적인 두 문자로 된 단어 목록에 대해 확인 합니다. 일치 항목을 찾을 수 없는 경우에는 단어를 머리글자어로 가정 합니다. 또한이 규칙은 이름에 4 개의 대문자 또는 이름의 끝에 있는 행의 3 개의 대문자를 포함 하는 경우 머리글자어를 발견 했다고 가정 합니다.

규칙에 따라 두 문자로 된 머리글자어는 모두 대문자를 사용 하 고 3 개 이상의 문자로 된 머리글자어는 파스칼식 대/소문자를 사용 합니다. 다음 예에서는이 명명 규칙을 사용 합니다. ' DB ', ' CR ', ' Cpa ' 및 ' Ecma '. 다음 예에서는 규칙을 위반 합니다. ' Io ', ' XML ' 및 ' DoD ', 매개 변수가 아닌 이름 (' xp ' 및 ' cpl ')의 경우

' I d '는이 규칙을 위반 하는 특별 한 대/소문자입니다. 'Id'는 머리글자어가 아니라 'identification'의 약어입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

대/소문자를 올바르게 변경 하려면 이름을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

고유한 명명 규칙을가지고 있거나 식별자가 회사 또는 기술 이름과 같이 적절 한 이름을 나타내는 경우이 경고를 표시 하는 것이 안전 합니다.

코드 분석 사용자 지정 사전에 특정 용어, 약어 및 머리글자어를 추가할 수도 있습니다. 사용자 지정 사전에 지정 된 용어는이 규칙의 위반을 발생 시 키 지 않습니다. 자세한 내용은 [방법: 코드 분석 사전을](../code-quality/how-to-customize-the-code-analysis-dictionary.md)사용자 지정 합니다.

## <a name="related-rules"></a>관련 규칙

[CA1708: 식별자는 대/소문자가 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)