---
title: 'CA1716: 식별자는 키워드와 달라야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9a51ac9509cf891c05166d46e4b72b862c0dc723
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547074"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: 식별자는 키워드와 달라야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

네임 스페이스, 형식 또는 가상 또는 인터페이스 멤버의 이름이 프로그래밍 언어의 예약 키워드와 일치 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 네임 스페이스, 형식 및 멤버만을 찾지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

네임 스페이스, 형식 및 가상 멤버와 인터페이스 멤버의 식별자는 공용 언어 런타임을 대상으로 하는 언어에서 정의 된 키워드와 일치 하면 안 됩니다. 사용 되는 언어 및 키워드에 따라 컴파일러 오류 및 모호성을 통해 라이브러리를 사용 하기 어려울 수 있습니다.

이 규칙은 다음 언어로 된 키워드를 검사 합니다.

- Visual Basic
- C#
- C++/CLI

대/소문자를 구분 하지 않는 비교는 Visual Basic 키워드에 사용 되 고 다른 언어에 대 한 대/소문자 구분 비교가 사용 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

키워드 목록에 표시 되지 않는 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

식별자가 API 사용자를 혼동 하지 않고 .NET의 사용 가능한 모든 언어에서 해당 라이브러리를 사용할 수 있음을 확신 하는 경우이 규칙에서 경고를 표시 하지 않을 수 있습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1716.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.