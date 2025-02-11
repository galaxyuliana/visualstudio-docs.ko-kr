---
title: 'CA1301: 중복 액셀러레이터 키를 사용하지 마십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 16cd44f00db13027d737b6a6b496877075ac6fa9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922274"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: 중복 액셀러레이터 키를 사용하지 마십시오.

|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|범주|Microsoft.Globalization|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인
형식은 리소스 파일 <xref:System.Windows.Forms.Control?displayProperty=fullName> 에 저장 된 것과 동일한 액세스 키를 가진 두 개 이상의 최상위 컨트롤을 확장 하 고 포함 합니다.

## <a name="rule-description"></a>규칙 설명

액셀러레이터 라고도 하는 액세스 키를 사용 하면 **Alt** 키를 사용 하 여 컨트롤에 대 한 키보드 액세스를 사용할 수 있습니다. 여러 컨트롤에 동일한 액세스 키가 있는 경우에는 액세스 키의 동작이 잘 정의 되지 않습니다. 사용자는 액세스 키를 사용 하 여 의도 한 컨트롤에 액세스 하지 못할 수 있으며 의도 한 컨트롤 외의 다른 컨트롤을 사용할 수 있습니다.

이 규칙의 현재 구현은 메뉴 항목을 무시 합니다. 그러나 동일한 하위 메뉴에 있는 메뉴 항목에는 동일한 액세스 키가 없어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 모든 컨트롤에 대해 고유한 액세스 키를 정의 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
다음 예제에서는 동일한 액세스 키를 가진 두 개의 컨트롤을 포함 하는 최소 폼을 보여 줍니다. 키는 리소스 파일에 저장 되며이는 표시 되지 않습니다. 그러나 해당 값은 주석 처리 `checkBox.Text` 된 줄에 표시 됩니다. 중복 된 액셀러레이터의 동작을 검사 하 여 해당 줄 `checkBox.Text` 을 주석 처리 된 항목과 교환할 수 있습니다. 그러나이 경우에는이 예제에서 규칙의 경고를 생성 하지 않습니다.

[!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [데스크톱 앱의 리소스](/dotnet/framework/resources/index)