---
title: 이름 지정 경고
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis warnings, naming warnings
- naming warnings
- warnings, naming
ms.assetid: f97223ce-1d39-4134-81c9-fff2c75d979b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90bdc70a2de900d43831994aff72e25031241cc3
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66715310"
---
# <a name="naming-warnings"></a>이름 지정 경고

이름 지정 경고.NET 디자인 지침의 명명 규칙 준수를 지원합니다.

## <a name="in-this-section"></a>섹션 내용

|규칙|설명|
|----------|-----------------|
|[CA1700: 열거형 값 ' 이름을 바꾸지 마십시오](../code-quality/ca1700-do-not-name-enum-values-reserved.md)|이 규칙에서는 "reserved"라는 단어가 포함된 이름을 갖는 열거형 멤버가 현재 사용되지는 않지만 이후 버전에서 이름이 바뀌거나 제거될 자리 표시자라고 가정합니다. 멤버의 이름을 바꾸거나 멤버를 제거하는 것은 주요 변경에 해당합니다.|
|[CA1713: 이벤트에는 before 또는 after 접두사 없어야](../code-quality/ca1713-events-should-not-have-before-or-after-prefix.md)|이벤트 이름이 "Before" 또는 "After"로 시작합니다. 특정 시퀀스에서 발생하는 관련 이벤트의 이름을 지정하려면 현재 또는 과거 시제를 사용하여 동작 시퀀스 내의 상대적인 위치를 나타냅니다.|
|[CA1714: 플래그 열거형에는 복수형 이름을 사용 해야 합니다.](../code-quality/ca1714-flags-enums-should-have-plural-names.md)|Public 열거형에 System.FlagsAttribute 특성이 및 해당 이름 "s"에서 끝나지 않습니다. FlagsAttribute로 표시 된 형식에는 둘 이상의 값을 지정할 수 있음을 나타내므로 특성에는 복수형 이름을 갖습니다.|
|[CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)|외부에서 볼 수 있는 식별자의 이름에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|
|[CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)|공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다.|
|[CA1715: 식별자에는 올바른 접두사를 사용 해야 합니다.](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)|외부에 표시 되는 인터페이스의 이름이 대문자 "I"로 시작 하지 않습니다.  에 외부적으로 노출 되는 형식 또는 메서드의 제네릭 형식 매개 변수의 이름을 대문자 "T"로 시작 하지 않습니다.|
|[CA1720: 식별자에 형식 이름을 포함 해야 합니다.](../code-quality/ca1720-identifiers-should-not-contain-type-names.md)|외부에 노출되는 멤버의 매개 변수 이름에 데이터 형식 이름이 포함되어 있거나 외부에 노출되는 멤버의 이름에 언어에 따라 다른 데이터 형식 이름이 포함되어 있습니다.|
|[CA1722: 식별자에는 잘못 된 접두사를 사용 해야 합니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)|규칙에 따라 특정 프로그래밍 요소에만 특정 접두사로 시작하는 이름을 사용할 수 있습니다.|
|[CA1711: 식별자에는 접미사를 사용 해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)|규칙에 따라 특정 기본 형식을 확장하거나 특정 인터페이스를 구현하는 형식의 이름 또는 이러한 형식에서 파생되는 형식의 이름만이 예약된 특정 접미사로 끝나야 합니다. 다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.|
|[CA1717: FlagsAttribute 열거형만 복수형 이름이 있어야 합니다.](../code-quality/ca1717-only-flagsattribute-enums-should-have-plural-names.md)|명명 규칙은 열거형 이름이 복수형인 경우 여러 열거 값을 동시에 지정할 수 있음을 나타내도록 되어 있습니다.|
|[CA1725: 매개 변수 이름은 기본 선언과 일치 해야 합니다.](../code-quality/ca1725-parameter-names-should-match-base-declaration.md)|재정의 계층 구조에서 매개 변수 이름을 일관되게 지정하면 메서드 재정의를 더 편리하게 사용할 수 있습니다. 파생된 메서드의 매개 변수 이름이 기본 선언의 이름과 다르면 메서드가 기본 메서드의 재정의인지 메서드의 새 오버로드인지를 혼동할 수 있습니다.|
|[CA1719: 매개 변수 이름은 멤버 이름과 일치 하지는](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)|매개 변수 이름 매개 변수의 의미를 나타내고 멤버 이름에는 멤버의 의미를 나타내야 합니다. 매개 변수와 멤버의 의미가 같게 디자인되는 경우는 드뭅니다. 매개 변수의 이름을 멤버 이름과 동일하게 지정하는 것은 비직관적이고 라이브러리 사용을 어렵게 만듭니다.|
|[CA1701: 리소스 문자열 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)|리소스 문자열의 각 단어는 대/소문자를 기반으로 하는 토큰으로 분할 됩니다. Microsoft 맞춤법 검사 라이브러리에서는 연속된 각 두 토큰의 조합을 검사합니다. 규칙 위반이 인식되면 단어에서 규칙 위반을 작성합니다.|
|[CA1703: 리소스 문자열에는 정확한 철자를 사용 해야](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)|리소스 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|
|[CA1724: 형식 이름은 네임 스페이스 달라 야 합니다.](../code-quality/ca1724-type-names-should-not-match-namespaces.md)|형식 이름.NET 네임 스페이스의 이름과 일치 하지 해야 합니다. 이 규칙 위반 라이브러리의 사용 가능성을 줄일 수 있습니다.|
|[CA1707: 식별자에는 밑줄 없어야 합니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)|규칙에 따라 식별자 이름에는 밑줄 문자(_)가 포함될 수 없습니다. 이 규칙에서는 네임스페이스, 형식, 멤버 및 매개 변수를 검사합니다.|
|[CA1721: 속성 이름은 get 메서드와 달라 야 합니다.](../code-quality/ca1721-property-names-should-not-match-get-methods.md)|public 또는 protected 멤버의 이름이 "Get"으로 시작하며 이름의 나머지 부분이 public 또는 protected 속성의 이름과 같습니다. "Get" 메서드와 속성은 서로가 분명히 구분되는 이름을 사용해야 합니다.|
|[CA1716: 식별자는 키워드와 일치](../code-quality/ca1716-identifiers-should-not-match-keywords.md)|네임스페이스 이름 또는 형식 이름이 프로그래밍 언어의 예약된 키워드와 일치합니다. 네임스페이스 및 형식에 대한 식별자는 공용 언어 런타임을 대상으로 하는 언어에서 정의된 키워드와 일치하면 안 됩니다.|
|[CA1726: 기본 설정된 용어를 사용 합니다.](../code-quality/ca1726-use-preferred-terms.md)|외부에서 볼 수 있는 식별자의 이름에 특정 용어가 포함되어 있는데, 이 용어에는 기본 설정된 대체 용어가 있습니다. 또는 이름에 "Flag"나 "Flags"라는 용어가 포함되어 있습니다.|
|[CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)|규칙에 따라 매개 변수 이름은 카멜식 대/소문자를 및 네임 스페이스, 형식을 사용 하 고 멤버 이름을 사용 파스칼식 대/소문자 구분 합니다.|
|[CA1702: 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)|식별자 이름에 여러 개의 단어가 포함되어 있으며 이 중 적어도 하나의 단어가 대/소문자를 정확하게 사용하지 않은 복합 단어인 것 같습니다.|
|[CA1712: 열거형 값 형식 이름의 접두사로 사용 하지 마세요](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)|열거형 멤버의 이름은 접두사로 사용 하지 않습니다 형식 이름을 있으므로 형식 정보는 개발 도구에서 제공 해야 합니다.|
|[CA1710: 식별자에는 올바른 접미사를 사용 해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)|규칙에 따라 특정 기본 형식을 확장 하거나 특정 인터페이스 또는 이러한 형식에서 파생 된 형식을 구현 하는 형식의 이름을 기본 형식 또는 인터페이스와 연결 된 접미사를 갖습니다.|