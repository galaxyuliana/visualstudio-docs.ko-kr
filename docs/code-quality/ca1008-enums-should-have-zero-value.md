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
ms.openlocfilehash: 502033d2adffd640d2af6ee8d36b0c0f3cd71472
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547937"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: 열거형에는 0 값이 있어야 합니다.

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|범주|Microsoft.Design|
|변경 수준|비-플래그 열거에 **None** 값을 추가 하 라는 메시지가 표시 되는 경우 중단-열거형 값의 이름을 바꾸거나 제거할 것인지 묻는 메시지가 표시 되 면입니다.|

## <a name="cause"></a>원인

를 적용 <xref:System.FlagsAttribute?displayProperty=fullName> 하지 않은 열거형은 값이 0 인 멤버를 정의 하지 않습니다. 또는 적용 <xref:System.FlagsAttribute> 된가 있는 열거형이 0 값을 포함 하지만 이름이 ' n o n e '이 아닌 멤버를 정의 합니다. 또는 열거형은 0이 아닌 여러 개의 멤버를 정의 합니다.

기본적으로이 규칙은 외부에서 볼 수 있는 열거만 보이지만 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

다른 값 형식과 마찬가지로 초기화 되지 않은 열거형의 기본값은 0입니다. 플래그가 지정 되지 않은 특성 사용 열거형은 기본값이 열거형의 유효한 값이 되도록 0 값을 가진 멤버를 정의 해야 합니다. 해당 하는 경우 멤버 이름을 ' n o n e '으로 합니다. 그렇지 않으면 가장 자주 사용 되는 멤버에 0을 할당 합니다. 기본적으로 선언에서 첫 번째 열거형 멤버의 값이 설정 되지 않은 경우 해당 값은 0입니다.

를 <xref:System.FlagsAttribute> 적용 한 열거형이 0 값의 멤버를 정의 하는 경우 열거형에 값이 설정 되지 않았음을 나타내려면 해당 이름이 ' n o n e ' 이어야 합니다. 다른 용도에 대해 0 값 멤버를 사용 하는 것은 및 및 비트 연산자 <xref:System.FlagsAttribute> 가 멤버와 쓸모가 없다는 점에서를 사용 하는 것과는 반대입니다. 이는 한 멤버만 값 0을 할당 해야 함을 의미 합니다. 플래그 특성이 지정 된 열거형에서 값이 0 인 멤버가 여러 개 발생 하는 `Enum.ToString()` 경우는 0이 아닌 멤버에 대해 잘못 된 결과를 반환 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

플래그가 지정 되지 않은 특성 사용 열거에 대 한이 규칙 위반 문제를 해결 하려면 값이 0 인 멤버를 정의 합니다. 이는 주요 변경 내용입니다. 0 값 멤버를 정의 하는 플래그 특성을 사용 하는 열거형의 경우이 멤버의 이름을 ' n o n e '으로 지정 하 고 값이 0 인 다른 멤버를 삭제 합니다. 이는 주요 변경 내용입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이전에 제공 된 플래그 특성을 사용 하는 열거형을 제외 하 고이 규칙에서 경고를 표시 하지 마십시오.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1008.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 규칙을 충족 하는 열거형 두 개와 규칙을 위반 `BadTraceOptions`하는 열거형을 보여 줍니다.

[!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
[!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
[!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>관련 규칙

- [CA2217: 열거형을 FlagsAttribute로 표시 하지 않습니다.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: 열거형 값의 이름을 ' Reserved '로 하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: 열거형 값에 형식 이름을 접두사로 사용 하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)
- [CA1028: Enum 저장소는 Int32 여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)
- [CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>참고자료

- <xref:System.Enum?displayProperty=fullName>