---
title: 'CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fae67f8c1ffa3b4e6d7cc2f0fbbaf670733f9ff4
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923303"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.

|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|범주|Microsoft.Design|
|변경 수준|해당 형식이 어셈블리 외부에 표시 되지 않는 경우에는 중단 되지 않습니다.<br /><br /> 중단-형식이 어셈블리 외부에 표시 되는 경우입니다.|

## <a name="cause"></a>원인
클래스가 <xref:System.IDisposable?displayProperty=fullName> 형식이 고 클래스가 구현 <xref:System.IDisposable>하지 않는 인스턴스 필드를 선언 하 고 구현 합니다.

## <a name="rule-description"></a>규칙 설명
클래스는 소유 하 <xref:System.IDisposable> 고 있는 관리 되지 않는 리소스를 삭제 하기 위해 인터페이스를 구현 합니다. <xref:System.IDisposable> 형식인 인스턴스 필드는 필드가 관리 되지 않는 리소스를 소유 함을 나타냅니다. <xref:System.IDisposable> 필드를 선언 하는 클래스는 관리 되지 않는 리소스를 간접적으로 소유 <xref:System.IDisposable> 하 고 인터페이스를 구현 해야 합니다. 클래스에서 관리 되지 않는 리소스를 직접 소유 하지 않는 경우 종료자를 구현 하지 않아야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 <xref:System.IDisposable> <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드에서 및를 구현 하 고 필드의 <xref:System.IDisposable.Dispose%2A> 메서드를 호출 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 규칙을 위반 하는 클래스와을 구현 <xref:System.IDisposable>하 여 규칙을 충족 하는 클래스를 보여 줍니다. 클래스는 관리 되지 않는 리소스를 직접 소유 하지 않으므로 종료자를 구현 하지 않습니다.

[!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
[!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>관련 규칙
[CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

[CA2216: 삭제 가능한 형식은 종료자를 선언 해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

[CA2215: Dispose 메서드는 기본 클래스 dispose를 호출 해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

[CA1049: 네이티브 리소스를 소유 하는 형식은 삭제 가능 해야 합니다.](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)