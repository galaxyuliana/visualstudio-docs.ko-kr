---
title: 'CA1008: 열거형에는 0 값이 있어야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4bb79d2944bdb49c59fd53fb30e1497c57c5c516
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57868287"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: 열거형에는 0 값이 있어야 합니다.

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|범주|Microsoft.Design|
|변경 수준|아님-한 경우 추가 메시지가 표시 되는 **없음** 비 플래그 열거형 값입니다. 주요-이름 바꾸기 또는 열거형 값을 제거 하는 메시지가 있습니다.|

## <a name="cause"></a>원인

적용 되지 않은 열거형 <xref:System.FlagsAttribute?displayProperty=fullName> 0 값을 가진 멤버를 정의 하지 않습니다. 또는 적용 된 열거형 <xref:System.FlagsAttribute> 멤버 정의 합니다. 값 0이 아닌 이름 '없음'입니다. 열거형은 여러 정의 또는 0 값을 가진 멤버입니다.

기본적으로이 규칙만 살펴봅니다 열거형 외부에서 볼 수 있지만 이것이 [구성할 수 있는](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

다른 값 형식과 마찬가지로 초기화 되지 않은 열거형의 기본값은 0입니다. 비-플래그 특성을 사용 하는 열거형을 기본 값이 열거형의 유효한 값이 되도록 0 값을 가진 멤버를 정의 해야 합니다. 해당 하는 경우 멤버의 이름을 '없음'입니다. 가장 자주 사용 되는 멤버에 0이 고, 그렇지 할당 합니다. 기본적으로 선언에서 첫 번째 열거형 멤버의 값을 설정 하지 않으면 해당 값이 0입니다.

경우에 열거형을 <xref:System.FlagsAttribute> 적용 값이 0 인 멤버를 정의 합니다. 해당 이름은 열거형에 값이 없는 설정 되어 있다고 나타내기 위해 ' 없음' 이어야 합니다. 다른 용도로 달리 사용에 대 한 값이 0 인 멤버를 사용 하는 <xref:System.FlagsAttribute> 에 AND 및 또는 비트 연산자는 멤버와 의미가 없습니다. 즉, 해당 멤버가 하나만 값 0을 할당 해야 합니다. 0 값을 가진 여러 멤버 플래그 특성을 사용 하는 열거형에 발생 하는 경우 `Enum.ToString()` 은 0이 아닌 멤버에 대 한 잘못 된 결과 반환 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

열거형 플래그 특성 사용에 대 한이 규칙 위반 문제를 해결 하려면 0의 값을 가진 멤버를 정의 합니다. 이 줄 바꿈하지 않는 변경 내용입니다. 플래그 특성을 사용 하는 열거형 값이 0 인 멤버를 정의 '없음'이 멤버 이름 및 0; 값이 있는 다른 멤버를 삭제 합니다. 주요 변경 내용입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

에 이전에 제공 된 플래그 특성을 사용 하는 열거형을 제외 하 고이 규칙에서 경고를 표시 하지 마십시오.

## <a name="configurability"></a>용이성

이 규칙을 실행 하는 경우 [FxCop 분석기](install-fxcop-analyzers.md) (통해서가 아닌 정적 코드 분석), 부분을 구성할 수 있습니다 프로그램에서이 규칙을 실행 하는 코드 베이스를 해당 액세스 가능성을 기준으로 합니다. 예를 들어 규칙 public이 아닌 API 화면에 대해서만 실행 되도록 지정, 프로젝트에서.editorconfig 파일에 다음 키-값 쌍 추가:

```
dotnet_code_quality.ca1008.api_surface = private, internal
```

이 범주 (디자인)에이 규칙에 대 한 모든 규칙에 대 한, 모든 규칙에 대해이 옵션을 구성할 수 있습니다. 자세한 내용은 [구성 FxCop 분석기](configure-fxcop-analyzers.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 규칙을 충족 하는 두 개의 열거형 및 열거형 `BadTraceOptions`, 규칙을 위반 하는 합니다.

[!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
[!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
[!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>관련된 규칙

- [CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: 열거형 값 ' 이름을 바꾸지 마십시오](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: 열거형 값 형식 이름의 접두사로 사용 하지 마세요](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)
- [CA1028: 열거형 저장소는 Int32 여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)
- [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.Enum?displayProperty=fullName>