---
title: 'CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 65bddd599bb544e000ca1d1269b84e53f51843bb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546074"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|범주|Microsoft.Interoperability|
|변경 수준|DependsOnFix|

## <a name="cause"></a>원인
 구성 요소 개체 모델 (COM)의 표시 형식이 COM에 표시 되지 않는 형식에서 파생 됩니다.

## <a name="rule-description"></a>규칙 설명
 COM 노출 형식 새 버전의 멤버를 추가 하면 현재 버전에 바인딩되는 COM 클라이언트의 중단을 방지 하려면 엄격한 지침을 따라야 합니다. COM에 표시 되지 않는 형식에 새 멤버를 추가할 때 이러한 COM 버전 관리 규칙을 수행 하지 않아도 가정 합니다. 그러나 COM 노출 하는 경우 COM 표시 되지 않는 형식에서 파생 형식과의 클래스 인터페이스도 노출 <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ClassInterfaceType> (기본값), 기본 형식의 모든 public 멤버나 (표시 되어 있지 않다면 특히 COM으로 보이지 않는, 하는 것은 중복) COM에 노출 됩니다. 이후 버전에서는 새 멤버를 추가 하는 기본 형식, 파생 된 유형의 클래스 인터페이스에 바인딩되는 모든 COM 클라이언트가 중단 될 수 있습니다. COM 노출 형식을 COM 클라이언트 손상의 가능성을 줄이기 위해 COM 노출 형식에서 파생 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 기본 COM 노출 형식 또는 파생 된 형식을 COM 표시 되지 않습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)