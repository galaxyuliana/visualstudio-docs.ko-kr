---
title: 'CA1409: Com 노출 형식을 만들 수 있어야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4197feae7f13e82ab786cbb901c9216fa1a98353
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996443"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Com 노출 형식을 만들 수 있어야 합니다.

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 특히 표시 구성 요소 개체 모델 (COM)에 표시 되는 참조 형식 매개 변수가 있는 public 생성자를 포함 하지만 (매개 변수가 없는) 공용 기본 생성자가 포함 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 COM 클라이언트에서 공용 기본 생성자가 없는 형식을 만들 수 없습니다. 그러나 형식 여전히 액세스할 수 있습니다 COM 클라이언트에서 다른 방법 예를 들어 (메서드 호출의 반환 값)를 통해 클라이언트에 전달 및 형식을 만들 수 있는 경우.

 규칙에서 파생 된 형식은 무시 <xref:System.Delegate?displayProperty=fullName>합니다.

 기본적으로 다음은 COM에 표시: 어셈블리, public 형식, 공용 인스턴스 멤버를 공용 형식 및 공개 값 형식의 모든 멤버입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 공용 기본 생성자를 추가 하거나 제거 합니다 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 형식에서입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 다른 방법으로 만들 COM 클라이언트에 개체를 전달 하는 제공 되는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고자료

- [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)