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
ms.openlocfilehash: 2763d7dd167ad0027509c44b8f9d43523f03976b
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547788"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: 적합한 속성을 사용하세요.

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

메서드의 이름이로 `Get`시작 하 고, 매개 변수를 사용 하지 않고, 배열이 아닌 값을 반환 하는 경우

기본적으로이 규칙은 공용 및 보호 된 메서드만 검색 하지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

대부분의 경우 속성은 데이터를 나타내고 메서드는 작업을 수행 합니다. 속성은 필드와 같은 액세스를 사용 하 여 더 쉽게 사용할 수 있습니다. 이러한 조건 중 하나가 있는 경우 메서드는 속성이 될 수 있는 좋은 후보입니다.

- 인수를 사용 하지 않고 개체의 상태 정보를 반환 합니다.

- 단일 인수를 수락 하 여 개체 상태의 일부를 설정 합니다.

속성은 필드인 것 처럼 동작 해야 합니다. 메서드를 사용할 수 없는 경우에는 속성으로 변경 하면 안 됩니다. 메서드는 다음과 같은 경우에 속성 보다 우수 합니다.

- 메서드는 시간이 많이 걸리는 작업을 수행 합니다. 메서드는 필드 값을 설정 하거나 가져오는 데 필요한 시간 보다 더 perceivably.

- 메서드는 변환을 수행 합니다. 필드에 액세스 하면 저장 된 데이터의 변환 된 버전이 반환 되지 않습니다.

- Get 메서드는 관찰 가능 파생 효과를 가집니다. 필드의 값을 검색 해도 부작용이 발생 하지 않습니다.

- 실행 순서는 중요 합니다. 필드의 값을 설정 해도 다른 작업의 발생에 의존 하지 않습니다.

- 메서드를 연속 해 서 두 번 호출 하면 다른 결과가 생성 됩니다.

- 메서드는 정적 이지만 호출자가 변경할 수 있는 개체를 반환 합니다. 필드의 값을 검색 하는 경우 호출자가 필드에 의해 저장 된 데이터를 변경할 수 없습니다.

- 메서드는 배열을 반환 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 메서드를 속성으로 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

메서드가 이전에 나열 된 조건 중 하나 이상을 충족 하는 경우이 규칙에서 경고를 표시 하지 않습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1024.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="control-property-expansion-in-the-debugger"></a>디버거의 컨트롤 속성 확장

프로그래머는 속성을 사용 하지 않는 한 가지 이유는 디버거가이를 자동으로 확장 하는 것을 원하지 않기 때문입니다. 예를 들어 속성에는 많은 개체를 할당 하거나 P/Invoke를 호출 하는 작업이 포함 될 수 있지만 실제로는 관찰 가능한 부작용이 없을 수 있습니다.

를 적용 <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>하 여 디버거가 자동 확장 속성을 방지할 수 있습니다. 다음 예에서는이 특성을 instance 속성에 적용 하는 방법을 보여 줍니다.

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

다음 예제에는 속성으로 변환 되어야 하는 몇 가지 메서드와 필드 처럼 동작 하지 않아야 하는 여러 메서드가 포함 되어 있습니다.

[!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]