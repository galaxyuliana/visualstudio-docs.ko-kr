---
title: 'CA1402: COM 노출 인터페이스에서 오버로드를 사용하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: aa45a54a994d19b1a04bc0785f21b88dfeef4475
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922120"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: COM 노출 인터페이스에서 오버로드를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|CheckId|CA1402|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
COM (구성 요소 개체 모델) 표시 인터페이스는 오버 로드 된 메서드를 선언 합니다.

## <a name="rule-description"></a>규칙 설명
오버로드된 메서드가 COM 클라이언트에 노출되면 첫 번째 메서드 오버로드만 이름이 유지됩니다. 후속 오버 로드는 이름에 밑줄 문자 ' _ '을 추가 하 고 오버 로드의 선언 순서에 해당 하는 정수를 추가 하 여 고유 하 게 이름을 바꿉니다. 예를 들어, 다음 메서드를 살펴보겠습니다.

```csharp
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

이러한 메서드는 다음과 같이 COM 클라이언트에 노출 됩니다.

```csharp
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

Visual Basic 6 COM 클라이언트는 이름에 밑줄을 사용 하 여 인터페이스 메서드를 구현할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 이름이 고유 하도록 오버 로드 된 메서드의 이름을 바꿉니다. 또는에서 액세스 가능성 `internal` 을 (`Friend` 에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])로 변경 하거나 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 특성을로 `false`설정 하 여 COM에서 인터페이스를 숨깁니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 인터페이스와 규칙을 충족 하는 인터페이스를 보여 줍니다.

[!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
[!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA1413: COM 노출 값 형식에 public이 아닌 필드를 사용 하지 마십시오.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

[CA1407: COM 노출 형식에 정적 멤버를 사용 하지 마십시오.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고자료

- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)
- [Long 데이터 형식](/dotnet/visual-basic/language-reference/data-types/long-data-type)