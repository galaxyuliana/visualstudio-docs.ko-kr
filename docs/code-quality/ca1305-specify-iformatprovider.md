---
title: 'CA1305: IFormatProvider를 지정하세요.'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: b96ca08b51bb5145357ef921bde753e133062203
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57868012"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: IFormatProvider를 지정하세요.

|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

메서드 또는 생성자를 받아들이는 오버 로드가 있는 하나 이상의 멤버를 호출을 <xref:System.IFormatProvider?displayProperty=fullName> 매개 변수 및 메서드 또는 생성자는 오버 로드를 호출 하지 않습니다는 <xref:System.IFormatProvider> 매개 변수입니다.

이 규칙 무시 무시로 설명 하는.NET Framework 메서드를 호출 하 여 <xref:System.IFormatProvider> 매개 변수입니다. 규칙에는 다음 메서드는 무시:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>규칙 설명

경우는 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> 또는 <xref:System.IFormatProvider> 개체가 제공 되지 않으면, 오버 로드 된 멤버에서 제공 하는 기본 값이 모든 로캘에서 원하는 효과 없을 수 있습니다. 또한.NET Framework 멤버 기본 문화권을 선택 하 고 코드에 대해 올바르지 않을 수 있다는 가정 하에 따라 서식 지정 합니다. 코드를 시나리오에 대 한 예상 대로 작동 하는지 확인 하려면 다음 지침에 따라 문화권별 형식 정보를 제공 해야 합니다.

- 사용자에 게 표시할 값을 현재 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>을 참조하세요.

- 값을 저장 하 고 (파일이 나 데이터베이스에 유지) 소프트웨어 액세스, 하는 경우 고정 문화권을 사용 합니다. <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>을 참조하세요.

- 값의 대상을 알 수 없는, 데이터 소비자 했거나 공급자 문화권을 지정 합니다.

오버 로드 된 멤버의 기본 동작에 맞게 적절 한 인 경우에 코드 자체 문서화 되 고 더 쉽게 유지 관리 되도록 문화권별 오버 로드를 명시적으로 호출 하는 것이 좋습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하는 오버 로드를 사용 하 여는 <xref:System.IFormatProvider> 인수입니다. 또는 사용 하 여는 [C# 문자열 보간](/dotnet/csharp/tutorials/string-interpolation) 에 전달 합니다 <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> 메서드.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

코드 유지 가능성이 중요 한 개발 우선 순위를 기본 형식으로 올바른 경우 및이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제

다음 코드에서는 `example1` CA1305 규칙을 위반 하는 문자열입니다. 합니다 `example2` 문자열이 전달 하 여 CA1305 규칙을 충족 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>를 구현 하는 <xref:System.IFormatProvider>를 <xref:System.String.Format(System.IFormatProvider,System.String,System.Object)?displayProperty=nameWithType>입니다. 합니다 `example3` 보간된 문자열을 전달 하 여 CA1305 규칙을 충족 하는 문자열 <xref:System.FormattableString.Invariant%2A?displayProperty=fullName]>합니다.

```csharp
string name = "Georgette";

// Violates CA1305
string example1 = String.Format("Hello {0}", name);

// Satisfies CA1305
string example2 = String.Format(CultureInfo.CurrentCulture, "Hello {0}", name);

// Satisfies CA1305
string example3 = FormattableString.Invariant($"Hello {name}");
```

## <a name="related-rules"></a>관련된 규칙

- [CA1304: CultureInfo를 지정 합니다.](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>참고자료

- [CultureInfo 클래스를 사용 하 여](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)