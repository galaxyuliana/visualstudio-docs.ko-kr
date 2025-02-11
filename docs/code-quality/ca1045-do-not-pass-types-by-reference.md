---
title: 'CA1045: 참조로 형식을 전달하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6fd0da0f8b04055622b46087ecb9f12b375d9576
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922855"
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045: 참조로 형식을 전달하지 마세요.

|||
|-|-|
|TypeName|DoNotPassTypesByReference|
|CheckId|CA1045|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
공용 형식의 public 또는 protected 메서드에 기본 형식, 참조 형식 `ref` 또는 기본 제공 형식 중 하나가 아닌 값 형식을 사용 하는 매개 변수가 있습니다.

## <a name="rule-description"></a>규칙 설명
`out` 또는`ref`를 사용 하 여 참조로 형식을 전달 하려면 포인터를 사용 하 고, 값 형식과 참조 형식이 어떻게 다른 지 이해 하 고, 여러 개의 반환 값이 있는 메서드를 처리 해야 합니다. 또한 `out` 와`ref` 매개 변수의 차이는 널리 이해 되지 않습니다.

참조 형식이 "참조로" 전달 되는 경우 메서드는 매개 변수를 사용 하 여 개체의 다른 인스턴스를 반환 합니다. 참조 형식을 참조로 전달 하는 것은 이중 포인터, 포인터에 대 한 포인터 또는 이중 간접 참조를 사용 하는 것으로도 알려져 있습니다. "값으로" 전달 되는 기본 호출 규칙을 사용 하 여 참조 형식을 사용 하는 매개 변수가 이미 개체에 대 한 포인터를 수신 합니다. 포인터가 가리키는 개체가 아닌 포인터는 값으로 전달 됩니다. 값으로 전달 하는 것은 메서드가 참조 형식의 새 인스턴스를 가리키기 위해 포인터를 변경할 수 없지만 포인터가 가리키는 개체의 콘텐츠를 변경할 수 있음을 의미 합니다. 대부분의 응용 프로그램의 경우이 방법은 충분 하며 원하는 동작을 생성 합니다.

메서드가 다른 인스턴스를 반환 해야 하는 경우 메서드의 반환 값을 사용 하 여이를 수행 합니다. 문자열에 <xref:System.String?displayProperty=fullName> 대해 작동 하 고 문자열의 새 인스턴스를 반환 하는 다양 한 메서드는 클래스를 참조 하세요. 이 모델을 사용 하면 원래 개체가 유지 되는지 여부를 결정 하는 호출자가 호출자에 게 남아 있습니다.

반환 값은 일반적이 고 많이 사용 되지만 `out` 및 `ref` 매개 변수의 올바른 응용 프로그램에는 중간 디자인 및 코딩 기술이 필요 합니다. 일반 사용자를 위해 디자인 한 라이브러리 설계자는 사용자가 `out` 또는 `ref` 매개 변수로 작업 하는 것을 원하지 않습니다.

> [!NOTE]
> 구조가 많은 매개 변수를 사용 하는 경우 이러한 구조체를 복사 하는 데 필요한 추가 리소스를 사용 하면 값으로 전달할 때 성능에 영향을 미칠 수 있습니다. 이러한 경우 또는 `out` 매개 변수를 사용 하 `ref` 는 것을 고려할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
값 형식으로 인해 발생 하는이 규칙 위반 문제를 해결 하려면 메서드가 개체를 반환 값으로 반환 하도록 합니다. 메서드가 여러 값을 반환 해야 하는 경우 값을 포함 하는 개체의 단일 인스턴스를 반환 하도록 다시 디자인 합니다.

참조 형식으로 인해 발생 하는이 규칙 위반 문제를 해결 하려면 원하는 동작이 참조의 새 인스턴스를 반환 하는지 확인 합니다. 인 경우 메서드는 반환 값을 사용 하 여이 작업을 수행 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시 하지 않아도 됩니다. 그러나이 디자인으로 인해 유용성 문제가 발생할 수 있습니다.

## <a name="example"></a>예제
다음 라이브러리에서는 사용자의 피드백에 대 한 응답을 생성 하는 클래스의 두 가지 구현을 보여 줍니다. 첫 번째 구현 (`BadRefAndOut`)은 라이브러리 사용자가 세 개의 반환 값을 강제로 관리 하도록 합니다. 두 번째 구현 (`RedesignedRefAndOut`)은 데이터를 단일 단위로 관리 하는 컨테이너 클래스 (`ReplyData`)의 인스턴스를 반환 하 여 사용자 환경을 단순화 합니다.

[!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_1.cs)]

## <a name="example"></a>예제
다음 응용 프로그램은 사용자의 환경을 보여 줍니다. 다시 디자인 된 라이브러리 (`UseTheSimplifiedClass` 메서드)를 호출 하는 것은 보다 간단 하며 메서드에서 반환 되는 정보는 쉽게 관리할 수 있습니다. 두 메서드의 출력은 동일 합니다.

[!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_2.cs)]

## <a name="example"></a>예제
다음 예제 라이브러리에서는 참조 형식 `ref` 에 대 한 매개 변수를 사용 하는 방법을 보여 주고이 기능을 구현 하는 더 나은 방법을 보여 줍니다.

[!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_3.cs)]

## <a name="example"></a>예제
다음 응용 프로그램은 라이브러리의 각 메서드를 호출 하 여 동작을 보여 줍니다.

[!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_4.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Changing pointer - passed by value:
12345
12345
Changing pointer - passed by reference:
12345
12345 ABCDE
Passing by return value:
12345 ABCDE
```

## <a name="related-rules"></a>관련 규칙
[CA1021: Out 매개 변수 방지](../code-quality/ca1021-avoid-out-parameters.md)