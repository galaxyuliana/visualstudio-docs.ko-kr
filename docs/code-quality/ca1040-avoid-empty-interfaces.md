---
title: 'CA1040: 빈 인터페이스를 사용하지 마세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 491923cb46100e9239b889024ade00022318b6cd
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547696"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: 빈 인터페이스를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

인터페이스는 멤버를 선언 하거나 둘 이상의 다른 인터페이스를 구현 하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 인터페이스만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

인터페이스에서는 동작이나 사용 계약을 제공하는 멤버를 정의합니다. 인터페이스에 의해 설명되는 기능은 상속 계층 구조에서 형식이 나타나는 위치에 관계없이 모든 형식에서 사용할 수 있습니다. 형식에서는 인터페이스의 멤버에 대한 구현을 제공하여 인터페이스를 구현합니다. 빈 인터페이스는 멤버를 정의 하지 않습니다. 따라서 구현할 수 있는 계약을 정의 하지 않습니다.

디자인에 형식이 구현 될 것으로 예상 되는 빈 인터페이스가 포함 된 경우에는 인터페이스를 표식으로 사용 하거나 형식 그룹을 식별 하는 방법으로 사용할 수 있습니다. 이 id가 런타임에 발생 하는 경우 사용자 지정 특성을 사용 하는 것이 올바른 방법입니다. 특성의 존재 여부 또는 특성의 속성을 사용 하 여 대상 유형을 식별할 수 있습니다. Id가 컴파일 타임에 발생 해야 하는 경우에는 빈 인터페이스를 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

인터페이스를 제거 하거나 멤버를 추가 합니다. 빈 인터페이스를 사용 하 여 형식 집합의 레이블을 지정 하는 경우 인터페이스를 사용자 지정 특성으로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

컴파일 시간에 형식 집합을 식별 하는 데 인터페이스를 사용 하는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1040.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 빈 인터페이스를 보여 줍니다.

[!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
[!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
[!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]