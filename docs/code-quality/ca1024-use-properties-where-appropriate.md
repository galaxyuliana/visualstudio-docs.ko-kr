---
title: 'CA1024: 적합한 속성을 사용하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bfedb55c0dcdb1077faea03bca56488ab3da1525
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842462"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: 적합한 속성을 사용하세요.

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

메서드를 시작 하는 이름을 가진 `Get`매개 변수가 없는 걸리고 배열이 아닌 값을 반환 합니다.

기본적으로이 규칙만 공용 및 보호 방법을 살펴보고, 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

대부분의 경우에서 속성 데이터 나타내고 메서드 작업을 수행 합니다. 속성에 액세스 하 여 쉽게 사용할 수 있도록 하는 필드와 유사 합니다. 메서드는 속성이 있는 경우 이러한 조건 중 하나가 될 수 있는 좋은 예는:

- 인수가 없는 하 고 개체의 상태 정보를 반환 합니다.

- 일부 개체의 상태를 설정 하려면 단일 인수를 수락 합니다.

속성 필드 처럼 동작 메서드가 없는 경우 속성에 변경 되지 해야 합니다. 다음과 같은 경우에는 속성 보다 더 나은 방법은 다음과 같습니다.

- 메서드는 시간이 많이 걸리는 작업을 수행합니다. 메서드는 필드의 값을 가져오거나 설정 하는 데 필요한 시간 보다 깁니다.

- 메서드는 변환을 수행 합니다. 필드 액세스를 저장 하는 데이터의 변환 된 버전을 반환 하지 않습니다.

- Get 메서드가 눈에 띄는 부작용입니다. 필드의 값을 검색 하는 경우에 부작용 생성 하지 않습니다.

- 실행 순서가 중요 합니다. 필드의 값을 설정 발생 한 다른 작업에 의존 하지 않습니다.

- 서로 다른 결과가 생성 메서드를 두 번 연속 해 서 호출 합니다.

- 메서드는 정적 이지만 호출자에 의해 변경 될 수 있는 개체를 반환 합니다. 필드의 값을 검색 필드로 저장 되는 데이터를 변경 하려면 호출자에 게를 허용 되지 않습니다.

- 메서드는 배열을 반환합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 속성에 메서드를 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

메서드 앞에 나열 된 조건 중 하나 이상 만족 하는 경우이 규칙에서 경고를 표시 합니다.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1024.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="control-property-expansion-in-the-debugger"></a>디버거에서 제어 속성 확장

자동 확장 하도록 디버거에 않으려는 프로그래머는 속성을 사용 하지 않도록 하는 이유 중 하나 이므로 해당 합니다. 예를 들어 큰 개체를 할당 또는 P/Invoke 호출 속성이 포함 될 수 있습니다 하지만 눈에 띄는 부작용 실제로 없는 경우.

적용 하 여 autoexpanding 속성에서 디버거를 방지할 수 있습니다 <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>합니다. 다음 예제에서는 인스턴스 속성에 적용 되 고이 특성을 보여 줍니다.

```vb
Imports System
Imports System.Diagnostics

Namespace Microsoft.Samples

    Public Class TestClass

        ' [...]

        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _
        Public ReadOnly Property LargeObject() As LargeObject
            Get
                ' Allocate large object
                ' [...]
            End Get
        End Property

    End Class

End Namespace
```

```csharp
using System;
using System.Diagnostics;

namespace Microsoft.Samples
{
    publicclass TestClass
    {
        // [...]

        [DebuggerBrowsable(DebuggerBrowsableState.Never)]
        public LargeObject LargeObject
        {
            get
            {
                // Allocate large object
                // [...]
            }
        }
    }
}
```

## <a name="example"></a>예제

다음 예제에서는 속성으로 변환 해야 하는 하며 몇몇은 필드 처럼 동작 하지 때문이 아니라 몇 가지 메서드를 포함 합니다.

[!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]