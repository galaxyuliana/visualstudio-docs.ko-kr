---
title: 'CA1412: ComSource 인터페이스를 IDispatch로 표시하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e0a7214ce37aa48d69b9261d686960fa0a4c308c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918649"
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: ComSource 인터페이스를 IDispatch로 표시하세요.

|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

형식으로 표시 됩니다는 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 특성 및 하나 이상의 지정 된 인터페이스로 표시 되지 합니다 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성이로 설정 합니다 `InterfaceIsDispatch` 값.

## <a name="rule-description"></a>규칙 설명

<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 구성 요소 개체 모델 (COM) 클라이언트에 클래스 노출 하는 이벤트 인터페이스를 식별 하는 데 사용 됩니다. 이러한 인터페이스를 노출 해야 `InterfaceIsIDispatch` Visual Basic 6 COM 클라이언트에서 이벤트 알림을 받을 수 있도록 합니다. 인터페이스를 사용 하 여 표시 되지 않으면 기본적으로는 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성 이중 인터페이스로 노출 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 추가 하거나 수정 합니다 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> InterfaceIsIDispatch를 사용 하 여 지정 된 모든 인터페이스에 대 한 해당 값이 설정 되도록 특성의 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 인터페이스 중 하나는 클래스를 보여 줍니다.

[!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
[!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]

## <a name="related-rules"></a>관련된 규칙

[CA1408: AutoDual ClassInterfaceType을 사용 하지 마십시오](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>참고자료

- [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)