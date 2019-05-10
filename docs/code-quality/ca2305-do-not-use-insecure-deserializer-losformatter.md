---
title: 'CA2305: 안전 하지 않은 LosFormatter 역직렬 변환기가 사용 하지 마세요'
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2305
- DoNotUseInsecureDeserializerLosFormatter
ms.openlocfilehash: 4e589bbea53dd6a73a6e6e4fc44b6cb397d6dcbd
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135461"
---
# <a name="ca2305-do-not-use-insecure-deserializer-losformatter"></a>CA2305: 안전 하지 않은 LosFormatter 역직렬 변환기가 사용 하지 마세요

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerLosFormatter|
|CheckId|CA2305|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

<xref:System.Web.UI.LosFormatter?displayProperty=nameWithType> deserialization 메서드를 호출 하거나 참조 합니다.

## <a name="rule-description"></a>규칙 설명

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

이 규칙을 찾습니다 <xref:System.Web.UI.LosFormatter?displayProperty=nameWithType> 메서드 호출 또는 참조를 역직렬화 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

[!INCLUDE[insecure-deserializers-fixes-for-always-insecure-deserializers](includes/insecure-deserializers-fixes-for-always-insecure-deserializers-md.md)]

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>의사 (pseudo) 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Web.UI;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        LosFormatter formatter = new LosFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Web.UI

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As LosFormatter = New LosFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```