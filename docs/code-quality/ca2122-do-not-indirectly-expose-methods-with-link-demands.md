---
title: 'CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8239b27cd92f66ae8f74ddb1accd95535bf56f93
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542339"
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.

|||
|-|-|
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|
|CheckId|CA2122|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public 또는 protected 멤버를 [링크 요구가](/dotnet/framework/misc/link-demands) 보안 검사는 수행 되지 않는 멤버에서 호출 됩니다.

## <a name="rule-description"></a>규칙 설명
 링크 요청은 직접 실행 호출자의 권한만 검사합니다. 구성원이 `X` 호출자와 호출 코드에서 보호 링크 요청이 있는 호출자에 게 필요한 권한을 사용할 수 없는 보안 요청을 사용 하면 `X` 보호 된 멤버에 액세스 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 추가 보안 [데이터 및 모델링](/dotnet/framework/data/index) 또는 링크 요청 멤버는 링크 요청으로 보호 되는 멤버 보안 되지 않은 액세스가 더 이상 제공 되도록 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서 경고를 안전 하 게 표시 하지 않으려면 있는 코드 부여 되지는 않습니다 호출자에 게 작업 또는 안전 하지 않은 방식으로 사용할 수 있는 리소스에 액세스 해야 합니다.

## <a name="example-1"></a>예제 1
 다음 예제에서는 규칙을 위반 하는 라이브러리 및 라이브러리의 약점을 보여 주는 응용 프로그램을 보여 줍니다. 예제 라이브러리를 함께 규칙을 위반 하는 두 메서드를 제공 합니다. `EnvironmentSetting` 메서드 환경 변수에 대 한 무제한 액세스에 대 한 링크 요청으로 보호 됩니다. 합니다 `DomainInformation` 메서드를 호출 하기 전에 호출자의 보안 요청을 통해 `EnvironmentSetting`합니다.

 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]

## <a name="example-2"></a>예제 2
 다음 응용 프로그램 보안이 설정 되지 않은 라이브러리 멤버를 호출 합니다.

 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
*Value from unsecured member: seattle.corp.contoso.com
```

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)