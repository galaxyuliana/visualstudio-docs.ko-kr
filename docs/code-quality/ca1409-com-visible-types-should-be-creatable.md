---
title: 'CA1409: Com 노출 형식을 만들 수 있어야 합니다.'
ms.date: 11/04/2016
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
ms.openlocfilehash: 4196cb91e1b866453de54347b8a67edd3dc2dc96
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921885"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Com 노출 형식을 만들 수 있어야 합니다.

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|범주|Microsoft.Interoperability|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
COM (구성 요소 개체 모델)에 표시 되는 것으로 특별히 표시 된 참조 형식에 매개 변수가 있는 공용 생성자가 포함 되어 있지만 매개 변수가 없는 공용 생성자가 포함 되어 있지 않습니다.

## <a name="rule-description"></a>규칙 설명
COM 클라이언트는 공용 기본 생성자가 없는 형식을 만들 수 없습니다. 그러나 형식을 만들어 클라이언트에 전달 (예: 메서드 호출의 반환 값을 통해) 할 수 있는 다른 방법이 있으면 COM 클라이언트에서 해당 형식을 계속 액세스할 수 있습니다.

규칙은에서 <xref:System.Delegate?displayProperty=fullName>파생 된 형식을 무시 합니다.

기본적으로 다음은 COM에 표시 됩니다. 어셈블리, public 형식, public 형식의 공용 인스턴스 멤버 및 public 값 형식의 모든 멤버입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 공용 기본 생성자를 추가 하거나 형식에서을 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
개체를 만들어 COM 클라이언트에 전달 하는 다른 방법이 제공 되는 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다.

## <a name="related-rules"></a>관련 규칙
[CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>참고자료

- [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)