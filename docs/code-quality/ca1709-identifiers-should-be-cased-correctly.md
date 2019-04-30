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
ms.openlocfilehash: f692218cd051338a6bd4e83a07d985bb52f907e6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546237"
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldBeCasedCorrectly|
|CheckId|CA1709|
|범주|Microsoft.Naming|
|변경 수준|주요-어셈블리, 네임 스페이스, 형식, 멤버 및 매개 변수에서 발생 한 경우입니다.<br /><br /> 주요 변경 아님-제네릭 형식 매개 변수에서 발생 한 경우|

## <a name="cause"></a>원인
 식별자의 이름은 올바르게 소문자 없습니다.

 \- 또는 -

 2 자 약어를 포함 하는 식별자의 이름 및 두 번째 문자가 소문자입니다.

 \- 또는 -

 3 개 이상의 대문자 머리 글자어를 포함 하는 식별자의 이름입니다.

## <a name="rule-description"></a>규칙 설명
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이 일관성 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 높이고 새 소프트웨어 라이브러리에 필요한 학습 곡선을 줄일 수 있습니다.

 규칙에 따라 매개 변수 이름은 카멜식 대/소문자를 및 네임 스페이스, 형식을 사용 하 고 멤버 이름을 사용 파스칼식 대/소문자 구분 합니다. 카멜식 대 / 소문자 이름에 첫 번째 문자는 소문자 및 이름에 나머지 단어의 첫 번째 문자가 대문자 인지 합니다. 카멜식 대 이름의 예로 `packetSniffer`, `ioFile`, 및 `fatalErrorCode`합니다. 파스칼식 대/소문자 이름에 첫 번째 문자를 대문자이 고 이름에 나머지 단어의 첫 번째 문자가 대문자 인지 합니다. 이름 파스칼식 대/소문자의 예로 `PacketSniffer`, `IOFile`, 및 `FatalErrorCode`합니다.

 이 규칙 이름을 대/소문자에 따라 단어로 분할 하 고 또는 "My"의 "In"와 같은 일반적인 2 자 단어의 목록에 대해 모든 두 글자 단어를 확인 합니다. 일치 하는 항목이 없으면 단어는 머리글자어로 간주 됩니다. 또한이 규칙 머리글자어 찾은 행에 4 개의 대문자 또는 대문자 이름의 끝에 행 3 이름이 포함 된 경우를 가정 합니다.

 규칙에 따라 2 자 약어는 모두 대문자로 사용 하 고 머리 글자어는 3 개 이상의 문자 사용 파스칼식 대/소문자 구분 합니다. 다음 예제에서는이 명명 규칙을 사용합니다. 'DB', 'CR', 'Cpa' 및 'Ecma'를 선택 합니다. 다음 예제에서는 규칙을 위반 합니다. 'Io', 'XML' 및 'DoD' 및 비-매개 변수 이름, 'xp' 및 ' c '에 대 한 합니다.

 'D'가이 규칙 위반을 특별 하 게 처리 합니다. 'Id'는 머리글자어가 아니라 'identification'의 약어입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 올바르게 소문자를 사용 하므로 이름을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 식별자를 나타내는 적절 한 이름, 회사의 기술 이름을 예를 들어 없거나 고유한 명명 규칙을 사용 하는 경우이 경고를 표시 하지 않아도 안전 합니다.

 특정 조건, 약어 및 머리글자어 추가할 수도 있습니다는 코드 분석 사용자 지정 사전입니다. 사용자 지정 사전에 지정 된 용어는이 규칙 위반을 발생 하지 않습니다. 자세한 내용은 [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)

## <a name="related-rules"></a>관련된 규칙
 [CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)