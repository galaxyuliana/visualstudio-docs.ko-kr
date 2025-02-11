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
ms.openlocfilehash: 9fd738b0c16ede4f71c001036546c335d8ca7186
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547041"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: 속성은 배열을 반환해서는 안 됩니다.

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|범주|Microsoft.Performance|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

속성은 배열을 반환 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 속성 및 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

속성이 읽기 전용 이더라도 속성이 반환 하는 배열은 쓰기 방지 되지 않습니다. 배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다. 일반적으로 사용자는 이러한 속성을 호출 하는 경우 성능에 부정적인 영향을 주지 않습니다. 특히 속성을 인덱싱된 속성으로 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 속성을 메서드로 설정 하거나 컬렉션을 반환 하도록 속성을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

<xref:System.Attribute> 클래스에서 파생 된 특성의 속성에 대해 발생 하는 경고를 표시 하지 않을 수 있습니다. 특성에는 배열을 반환 하는 속성이 포함 될 수 있지만 컬렉션을 반환 하는 속성은 포함할 수 없습니다.

속성이 [DTO (데이터 전송 Object)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) 클래스의 일부인 경우 경고를 표시 하지 않을 수 있습니다.

그렇지 않으면이 규칙에서 경고를 표시 하지 않습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1819.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나 모든 규칙에 대해이 옵션을 구성 하거나이 범주 (성능)의 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example-violation"></a>위반 예

다음 예제에서는이 규칙을 위반 하는 속성을 보여 줍니다.

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

이 규칙 위반 문제를 해결 하려면 속성을 메서드로 설정 하거나 배열 대신 컬렉션을 반환 하도록 속성을 변경 합니다.

### <a name="change-the-property-to-a-method"></a>속성을 메서드로 변경 합니다.

다음 예제에서는 속성을 메서드로 변경 하 여 위반을 수정 합니다.

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>컬렉션을 반환 하려면 속성을 변경 합니다.

다음 예제에서는를 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>반환 하도록 속성을 변경 하 여 위반을 수정 합니다.

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>사용자가 속성을 수정할 수 있도록 허용

클래스의 소비자가 속성을 수정할 수 있도록 허용 하는 것이 좋습니다. 다음 예제에서는이 규칙을 위반 하는 읽기/쓰기 속성을 보여 줍니다.

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

다음 예제에서는를 <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>반환 하도록 속성을 변경 하 여 위반을 수정 합니다.

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>관련 규칙

- [CA1024: 적절 한 경우 속성 사용](../code-quality/ca1024-use-properties-where-appropriate.md)