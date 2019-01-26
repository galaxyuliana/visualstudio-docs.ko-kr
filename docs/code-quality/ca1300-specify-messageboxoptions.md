---
title: 'CA1300: MessageBoxOptions를 지정하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0000b66302e0dbb549b2832210573d1b3b174b84
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54943275"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: MessageBoxOptions를 지정하세요.

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

메서드 호출의 오버 로드는 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> 메서드를 사용 하지 않는 한 <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> 인수.

## <a name="rule-description"></a>규칙 설명

오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 대 한 잘못 된 메시지 상자를 표시 하려면 전달 된 [MessageBoxOptions.RightAlign](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>) 및 [MessageBoxOptions.RtlReading](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>) 필드를 <xref:System.Windows.Forms.MessageBox.Show%2A> 메서드입니다. 검사는 <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> 오른쪽에서 왼쪽 읽기 순서를 사용할지 여부를 확인 하려면 포함 하는 컨트롤의 속성입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 오버 로드를 호출 합니다 <xref:System.Windows.Forms.MessageBox.Show%2A> 사용 하는 메서드를 <xref:System.Windows.Forms.MessageBoxOptions> 인수입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 대 한 코드 라이브러리를 지역화할 수는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제

다음 예제에서는 문화권의 읽기 순서에 대 한 적합 한 옵션이 있는 메시지 상자를 표시 하는 메서드를 보여 줍니다. 표시 되지 않는 리소스 파일, 예제를 빌드하려면 필요 합니다. 리소스 파일 없이 예제를 빌드하려면 및 오른쪽에서 왼쪽 기능을 테스트 하려면 예제의 주석을 따르세요.

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [데스크톱 앱의 리소스(.NET Framework)](/dotnet/framework/resources/index)