---
title: 'CA1819: 속성은 배열을 반환해서는 안 됩니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2824be0ecc29965abb68519aaa8eb8a83af8e688
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841375"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: 속성은 배열을 반환해서는 안 됩니다.

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|범주|Microsoft.Performance|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

속성이 배열을 반환합니다.

기본적으로이 규칙만 외부에서 표시 되는 속성 및 형식 처럼 보이지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

속성에서 반환 된 배열은 속성이 읽기 전용인 경우에는 읽기 전용인 지 않습니다. 배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다. 일반적으로 사용자가 성능에 부정적인 영향 이러한 속성을 호출 하는 이해할 수 없습니다. 특히 인덱싱된 속성으로 속성을 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 속성 메서드를 만들려면 하거나 컬렉션을 반환 하려면 속성을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

파생 되는 특성의 속성에 대해 발생 하는 경고를 표시 하지 않을 수는 <xref:System.Attribute> 클래스입니다. 특성은 배열을 반환 하는 속성을 포함할 수 있지만 컬렉션을 반환 하는 속성을 포함할 수 없습니다.

속성의 일부인 경우 경고를 표시 하지 않을 수는 [데이터 전송 개체 (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) 클래스입니다.

그렇지 않은 경우이 규칙에서 경고를 표시 하지 마십시오.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```ini
dotnet_code_quality.ca1819.api_surface = private, internal
```

이 범주 (성능)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example-violation"></a>예제 위반

다음 예제에서는이 규칙을 위반 하는 속성을 보여 줍니다.

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

이 규칙 위반 문제를 해결 하려면 속성 메서드를 만들려면 하거나 배열 대신 컬렉션을 반환 하려면 속성을 변경 합니다.

### <a name="change-the-property-to-a-method"></a>메서드로 속성 변경

다음 예제에서는 메서드에 속성을 변경 하 여 위반 문제를 해결 합니다.

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>컬렉션을 반환 하려면 속성 변경

다음 예에서는 반환할 속성을 변경 하 여 위반을 수정 된 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>:

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>속성을 수정 하는 작업을 할 수 있습니다.

속성을 수정 하려면 클래스의 소비자를 허용 하도록 좋습니다. 다음 예제에서는이 규칙을 위반 하는 읽기/쓰기 속성을 보여 줍니다.

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

다음 예에서는 반환할 속성을 변경 하 여 위반을 수정 된 <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>:

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>관련된 규칙

- [CA1024: 적절 한 속성을 사용 합니다.](../code-quality/ca1024-use-properties-where-appropriate.md)