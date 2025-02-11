---
title: 'CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d83da42a029d746899bfaccf5d62f8856a040611
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921113"
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.

|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
형식에 선언적 보안이 있고 해당 메서드 중 하나에 동일한 보안 작업에 대 한 선언적 보안이 있고, 보안 작업에 [링크 요청이](/dotnet/framework/misc/link-demands)없고, 형식에 의해 확인 된 사용 권한이 메서드로 확인 된 사용 권한의 하위 집합이 아닌 경우

## <a name="rule-description"></a>규칙 설명
메서드에는 동일한 작업에 대 한 메서드 수준과 형식 수준의 선언적 보안이 모두 포함 되어서는 안 됩니다. 두 검사는 결합 되지 않습니다. 메서드 수준 수요만 적용 됩니다. 예를 들어, 형식이 권한을 `X`요청 하 고 해당 메서드 중 하나가 권한을 `Y`요청 하는 경우 코드는 메서드를 실행할 수 `X` 있는 권한이 필요 하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
코드를 검토 하 여 두 동작이 모두 필요한 지 확인 합니다. 두 작업을 모두 수행 해야 하는 경우 메서드 수준 작업에 형식 수준에서 지정 된 보안이 포함 되어 있는지 확인 합니다. 예를 `X`들어 형식에서 권한을 요청 하 고 해당 메서드에 권한도 `Y`요청 해야 하는 경우이 메서드는 및 `Y`을 `X` 명시적으로 요청 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
메서드에 형식으로 지정 된 보안이 필요 하지 않은 경우에는이 규칙에서 경고를 표시 하지 않는 것이 안전 합니다. 그러나이는 일반적인 시나리오가 아니므로 신중 하 게 디자인을 검토 해야 하는 경우를 나타낼 수 있습니다.

## <a name="example-1"></a>예제 1

다음 예제에서는 환경 사용 권한을 사용 하 여이 규칙을 위반 하는 위험을 보여 줍니다. 이 예제에서 응용 프로그램 코드는 형식에 필요한 사용 권한을 거부 하기 전에 보안 형식의 인스턴스를 만듭니다. 실제 위협 시나리오에서는 응용 프로그램에서 개체의 인스턴스를 가져오는 다른 방법이 필요 합니다.

다음 예제에서는 라이브러리에서 메서드에 대 한 읽기 권한 및 형식에 대 한 쓰기 권한을 요청 합니다.

[!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example-2"></a>예제 2

다음 응용 프로그램 코드는 형식 수준 보안 요구 사항을 충족 하지 않는 경우에도 메서드를 호출 하 여 라이브러리의 취약성을 보여 줍니다.

[!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
[All permissions] Personal information: 6/16/1964 12:00:00 AM
[No write permission (demanded by type)] Personal information: 6/16/1964 12:00:00 AM
[No read permission (demanded by method)] Could not access personal information: Request failed.
```

## <a name="see-also"></a>참고자료

- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)
- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)