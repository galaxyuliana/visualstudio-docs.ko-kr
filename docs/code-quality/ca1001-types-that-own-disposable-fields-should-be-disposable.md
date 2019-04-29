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
ms.openlocfilehash: 581bc75c22326275dcb3657910f60c2977094037
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779748"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.

|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님-형식 어셈블리 외부에 표시 되지 않으면<br /><br /> 주요-형식이 어셈블리 외부에 표시 하는 경우입니다.|

## <a name="cause"></a>원인
 클래스 선언 및 구현 된 인스턴스 필드를 <xref:System.IDisposable?displayProperty=fullName> 형식 및 클래스를 구현 하지 않습니다 <xref:System.IDisposable>합니다.

## <a name="rule-description"></a>규칙 설명
 클래스에서 구현 하는 <xref:System.IDisposable> 인터페이스를 소유 하는 관리 되지 않는 리소스를 삭제 합니다. 인스턴스 필드는 <xref:System.IDisposable> 형식 필드 관리 되지 않는 리소스를 소유 하는지 나타냅니다. 선언 하는 클래스는 <xref:System.IDisposable> 필드에서 간접적으로 관리 되지 않는 리소스를 소유 하 고 구현 해야 합니다 <xref:System.IDisposable> 인터페이스입니다. 클래스는 관리 되지 않는 리소스를 직접 소유 하지 않습니다, 경우 종료자를 구현 하지 않아야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 구현 <xref:System.IDisposable> 들어오고를 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 메서드 호출을 <xref:System.IDisposable.Dispose%2A> 필드의 메서드.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 클래스 및 구현 하 여 규칙을 충족 하는 클래스 <xref:System.IDisposable>합니다. 클래스는 클래스에서 관리 되지 않는 리소스를 직접 소유 하지 않기 때문에 종료자를 구현 하지 않습니다.

 [!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
 [!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2216: 삭제 가능한 형식은 종료자를 선언 해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA2215: Dispose 메서드는 기본 클래스 dispose를 호출 해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA1049: 네이티브 리소스가 있는 형식은 삭제 가능 해야 합니다.](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)