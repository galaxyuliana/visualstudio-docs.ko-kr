---
title: 'CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0d5afd33ffb73c47b0f373f70c56166dbfced6d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547132"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다.

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

메서드 재정의의 매개 변수 이름이 메서드의 기본 선언에 있는 매개 변수 이름 또는 메서드의 인터페이스 선언에 있는 매개 변수의 이름과 일치 하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 메서드만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

재정의 계층 구조에서 매개 변수 이름을 일관되게 지정하면 메서드 재정의를 더 편리하게 사용할 수 있습니다. 파생된 메서드의 매개 변수 이름이 기본 선언의 이름과 다르면 메서드가 기본 메서드의 재정의인지 메서드의 새 오버로드인지를 혼동할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 매개 변수의 이름을 기본 선언과 일치 하도록 바꿉니다. 해결 방법은 COM 노출 메서드의 주요 변경 사항입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이전에 제공 된 라이브러리의 COM 노출 메서드를 제외 하 고이 규칙에서 경고를 표시 하지 마십시오.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1725.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.