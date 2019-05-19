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
ms.openlocfilehash: 47bbb39cadb6a092f71ebd7b3907f34fcc2782ce
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842043"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: 식별자는 키워드와 달라야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

네임 스페이스, 형식 이름 또는 가상 또는 인터페이스 멤버에는 프로그래밍 언어로 예약 된 키워드와 일치 합니다.

기본적으로이 규칙만 살펴봅니다 외부에 표시 되는 네임 스페이스, 형식 및 멤버 이지만 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

네임 스페이스, 형식에 대 한 식별자 및 가상 인터페이스 멤버는 공용 언어 런타임을 대상으로 하는 언어에서 정의 된 키워드와 일치 하 고 있습니다. 사용 되는 언어 및 키워드에 따라 컴파일러 오류와 모호성이 라이브러리를 사용 하 여 어려워질 수 있습니다.

이 규칙은 다음 언어의 키워드를 확인합니다.

- Visual Basic
- C#
- C++/CLI

Visual Basic 키워드 대/소문자 구분 비교를 사용 하 고 다른 언어는 대/소문자 구분 비교를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

키워드 목록에 나타나지 않는 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

식별자가 API의 사용자를 혼동 하지 않습니다 하 고 라이브러리를.NET에서 사용 가능한 모든 언어에서 사용할 수 있는지 확신 하는 경우이 규칙에서 경고를 무시할 수 있습니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1716.api_surface = private, internal
```

이 범주 (이름 지정)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.