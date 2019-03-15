---
title: 'CA1304: CultureInfo를 지정하세요.'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyCultureInfo
- CA1304
helpviewer_keywords:
- SpecifyCultureInfo
- CA1304
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1fe4ebce3a49c4aa626515e22eacd1c8e263847
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57870375"
---
# <a name="ca1304-specify-cultureinfo"></a>CA1304: CultureInfo를 지정하세요.

|||
|-|-|
|TypeName|SpecifyCultureInfo|
|CheckId|CA1304|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

메서드 또는 생성자 호출을 받아들이는 오버 로드가 있는 멤버를 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> 매개 변수 및 메서드 또는 생성자는 오버 로드를 호출 하지 않습니다는 <xref:System.Globalization.CultureInfo> 매개 변수입니다. 이 규칙에는 다음 방법에 대 한 호출 무시:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>규칙 설명

경우는 <xref:System.Globalization.CultureInfo> 또는 <xref:System.IFormatProvider?displayProperty=nameWithType> 개체가 제공 되지 않으면, 오버 로드 된 멤버에서 제공 하는 기본 값이 모든 로캘에서 원하는 효과 없을 수 있습니다. 또한.NET Framework 멤버 기본 문화권을 선택 하 고 코드에 대해 올바르지 않을 수 있다는 가정 하에 따라 서식 지정 합니다. 코드 시나리오에 대 한 예상 대로 작동을 위해 다음 지침에 따라 문화권별 형식 정보를 제공 해야 합니다.

- 사용자에 게 표시할 값을 현재 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>을 참조하세요.

- 값을 저장 하 고 소프트웨어 액세스, 경우 즉, 파일 또는 데이터베이스에 유지 고정 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>을 참조하세요.

- 값의 대상을 알 수 없는, 데이터 소비자 했거나 공급자 문화권을 지정 합니다.

오버 로드 된 멤버의 기본 동작에 맞게 적절 한 인 경우에 코드 자체 문서화 되 고 더 쉽게 유지 관리 되도록 문화권별 오버 로드를 명시적으로 호출 하는 것이 좋습니다.

> [!NOTE]
> <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 인스턴스를 사용 하 여 지역화 된 리소스를 검색할 때에 사용 되며는 <xref:System.Resources.ResourceManager?displayProperty=nameWithType> 클래스입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 오버 로드를 사용 하 여는 <xref:System.Globalization.CultureInfo> 인수입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

코드 유지 가능성이 중요 한 개발 우선 순위를 기본 문화권에 적합 한가 것이 확실 한 경우 및이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example-showing-how-to-fix-violations"></a>위반 문제를 해결 하는 방법을 보여 주는 예제

다음 예에서 `BadMethod` 이 규칙을 두 번 위반 합니다. `GoodMethod` 고정 문화권을 전달 하 여 첫 번째 위반을 수정 <xref:System.String.Compare%2A?displayProperty=nameWithType>, 하 고 현재 문화권을 전달 하 여 두 번째 위반 수정 <xref:System.String.ToLower%2A?displayProperty=nameWithType> 있으므로 `string3` 사용자에 게 표시 됩니다.

[!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_1.cs)]

## <a name="example-showing-formatted-output"></a>서식 있는 출력을 보여 주는 예제

다음 예제에서는 기본 현재 문화권의 결과 보여 줍니다 <xref:System.IFormatProvider> 으로 선택 되어 있는 <xref:System.DateTime> 형식입니다.

[!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
6/4/1900 12:15:12 PM
06/04/1900 12:15:12
```

## <a name="related-rules"></a>관련된 규칙

- [CA1305: IFormatProvider를 지정 합니다.](../code-quality/ca1305-specify-iformatprovider.md)

## <a name="see-also"></a>참고자료

- [CultureInfo 클래스를 사용 하 여](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)