---
title: 'CA2213: 삭제 가능한 필드는 삭제해야 합니다.'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b38157fcc23561b47a919151aa78a71f98b3909b
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65805008"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: 삭제 가능한 필드는 삭제해야 합니다.

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

구현 하는 형식을 <xref:System.IDisposable?displayProperty=fullName> 도 구현 하는 형식의 필드를 선언 <xref:System.IDisposable>합니다. 합니다 <xref:System.IDisposable.Dispose%2A> 필드의 메서드가 호출 되지 않습니다는 <xref:System.IDisposable.Dispose%2A> 메서드의 선언 형식입니다.

## <a name="rule-description"></a>규칙 설명

형식은 관리 되지 않는 해당 리소스를 모두 삭제 하는 일을 담당 합니다. 삭제 가능한 형식 되는지 여부를 CA2213 검사 규칙 (구현 하는, 즉 하나 <xref:System.IDisposable>) `T` 필드를 선언 `F` 삭제 가능 형식의 인스턴스인 `FT`합니다. 각 필드에 대 한 `F` 메서드를 포함 하는 형식의 이니셜라이저 내에서 로컬로 생성된 된 개체에 할당 하는 `T`, 규칙에 대 한 호출을 찾으려고 시도 `FT.Dispose`합니다. 호출할 메서드를 검색 하는 규칙이 `T.Dispose` 및 한 수준 아래 (호출한 메서드에 의해 호출 된 메서드 즉, `T.Dispose`).

> [!NOTE]
> 이외의 합니다 [특별 한 경우](#special-cases), 규칙을 포함 하는 형식의 메서드 및 이니셜라이저 내에서 로컬로 생성된 된 삭제 가능한 개체에 할당 된 필드에 대해서만 CA2213 발생 합니다. 개체를 만들거나 형식 외부에서 할당 된 경우 `T`, 규칙이 발생 하지 않습니다. 이 경우 포함 하는 형식 개체의 삭제에 대 한 책임을 소유 하지 않는 위치에 대 한 노이즈를 줄입니다.

### <a name="special-cases"></a>특별 한 경우

할당 개체를 로컬로 만들어지지 하는 경우에 다음 형식의 필드에 대 한 규칙 CA2213 발생할 수도 있습니다.

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

이러한 형식의 개체 생성자에 전달 하 고 다음 필드에 할당을 *소유권 양도 dispose* 새로 생성 된 형식입니다. 즉, 새로 생성된 된 형식의 개체를 삭제 하기 위한 책임 되었습니다. 개체 삭제 되지 않습니다 CA2213 위반이 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 호출 <xref:System.IDisposable.Dispose%2A> 구현 하는 형식의 필드에 <xref:System.IDisposable>입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

- 필드에서 보유 하는 리소스를 해제에 대 한 플래그가 지정 된 유형이 책임이 아닙니다 (즉, 형식에 없는 *소유권 dispose*)
- 에 대 한 호출 <xref:System.IDisposable.Dispose%2A> 규칙 검사 보다 더 깊은 수준 호출

## <a name="example"></a>예제

다음 코드 조각은 형식을 보여 줍니다 `TypeA` 구현 하는 <xref:System.IDisposable>합니다.

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

다음 코드 조각은 형식을 보여 줍니다 `TypeB` 필드를 선언 하 여 CA2213 규칙을 위반 하 `aFieldOfADisposableType` 삭제 가능한 형식으로 (`TypeA`) 호출 하지 <xref:System.IDisposable.Dispose%2A> 필드입니다.

[!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.IDisposable?displayProperty=fullName>
- [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)