---
title: 'CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b047669b962d5e38cd37132f84ae653ba30f9dc
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547301"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

식별자에 잘못 된 접미사가 있습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 식별자만 찾지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

규칙에 따라 특정 기본 형식을 확장 하거나 특정 인터페이스를 구현 하는 형식의 이름 또는 이러한 형식에서 파생 된 형식을 특정 예약 접미사로 끝나야 합니다. 다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.

다음 표에서는 예약 된 접미사와 여기에 연결 된 기본 형식 및 인터페이스를 보여 줍니다.

|접미사|기본 형식/인터페이스|
|------------|--------------------------|
|특성|<xref:System.Attribute?displayProperty=fullName>|
|Collection|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Dictionary|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|이벤트 처리기|이벤트 처리기 대리자|
|예외|<xref:System.Exception?displayProperty=fullName>|
|사용 권한|<xref:System.Security.IPermission?displayProperty=fullName>|
|큐|<xref:System.Collections.Queue?displayProperty=fullName>|
|스택|<xref:System.Collections.Stack?displayProperty=fullName>|
|스트림|<xref:System.IO.Stream?displayProperty=fullName>|

또한 다음 접미사를 사용 하면 안 됩니다.

- `Delegate`

- `Enum`

- `Impl`(대신 `Core` 사용)

- `Ex`동일한 형식의 이전 버전과 구분 하기 위한 유사 접미사

명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 대 한 일반적인 모양을 제공 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요한 학습 곡선이 줄어들고, 관리 코드 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 했을 때 고객의 자신감을 높일 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

형식 이름에서 접미사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

접미사가 애플리케이션 도메인에서 명확한 의미를 갖지 않는 한 이 규칙의 경고를 숨기지 마십시오.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1711.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (명명). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="related-rules"></a>관련 규칙

- [CA1710: 식별자에는 올바른 접미사가 있어야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>참고자료

- [특성](/dotnet/standard/design-guidelines/attributes)
- [이벤트 처리 및 발생](/dotnet/standard/events/index)