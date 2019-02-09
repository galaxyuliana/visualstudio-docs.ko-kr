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
ms.openlocfilehash: 623416e557759ace1ad6403ef8ef977df01da39e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911132"
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.

|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식에 선언적 보안 및 해당 메서드 중 하나에 동일한 보안 작업에 대 한 선언적 보안 및 보안 작업은 없습니다 [링크 요구가](/dotnet/framework/misc/link-demands)를 유형별로 검사 하는 권한이 없는 권한의 하위 집합 메서드에서 확인합니다.

## <a name="rule-description"></a>규칙 설명
 메서드 모두 동일한 동작에 대해 메서드 수준과 형식 수준의 선언적 보안 없어야 합니다. 두 개의 검사 결합 되지 않습니다. 메서드 수준 요청에만 적용 됩니다. 예를 들어 권한을 요구 하는 형식을 `X`, 및 권한을 요구 하는 방법 중 하나 `Y`, 코드 권한이 없는 `X` 메서드를 실행 하 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 두 작업이 필요한 지 확인 하도록 코드를 검토 합니다. 두 작업이 필요한 경우 메서드 수준 동작 형식 수준에서 지정 된 보안 포함 되는지 확인 합니다. 예를 들어 권한을 요구 하는 형식을 `X`, 및 권한을 요청 해야 `Y`, 메서드를 명시적으로 요청 해야 `X` 및 `Y`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 메서드는 형식에서 지정한 보안 필요가 없는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 그러나이 일반적인 시나리오가 되지 않으며 신중 하 게 설계 검토에 대 한 필요성을 나타낼 수 있습니다.

## <a name="example-1"></a>예제 1

다음 예제에서는이 규칙을 위반의 위험을 보여 주기 위해 환경 권한을 사용 합니다. 이 예제에서는 응용 프로그램 코드는 형식에 필요한 사용 권한 거부 하기 전에 보안 된 형식의 인스턴스를 만듭니다. 위협 현실적인 시나리오에서는 응용 프로그램에는 개체의 인스턴스를 가져올 다른 방법이 필요 합니다.

다음 예에서 라이브러리 요구 사항 형식에 대 한 권한을 읽고 쓰는 메서드에 대 한 사용 권한.

[!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example-2"></a>예제 2

다음 응용 프로그램 코드를 사용 하는 형식 수준 보안 요구 사항을 충족 하지도 메서드를 호출 하 여 라이브러리의 취약점으로 인 한을 보여줍니다.

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