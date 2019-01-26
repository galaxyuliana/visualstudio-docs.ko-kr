---
title: 'CA2108: 값 형식에서 선언적 보안을 검토하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
helpviewer_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb7795b2e1cdcdf8d32578396bb879f4573a45e8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55003289"
---
# <a name="ca2108-review-declarative-security-on-value-types"></a>CA2108: 값 형식에서 선언적 보안을 검토하십시오.

|||
|-|-|
|TypeName|ReviewDeclarativeSecurityOnValueTypes|
|CheckId|CA2108|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

Public 또는 protected 값 형식이로 보호 되는 [데이터 및 모델링](/dotnet/framework/data/index) 또는 [링크 요구가](/dotnet/framework/misc/link-demands)합니다.

## <a name="rule-description"></a>규칙 설명

값 형식 할당 되 고 다른 생성자를 실행 하기 전에 해당 기본 생성자에서 초기화 됩니다. 값 형식이 요청 또는 LinkDemand를 통해 보안이 유지 되 고 호출자에 게 이외의 모든 생성자 보안 검사를 충족 하는 권한이 없는 경우 기본값을 실패 하 고 보안 예외가 throw 됩니다. 값 형식 할당이 해제 되지 않습니다. 기본 생성자에서 설정 된 상태에서 중단 됩니다. 값 형식의 인스턴스를 전달 하는 호출자가 만들거나 인스턴스에 액세스 권한이 있는지를 가정 하지 마십시오.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

형식에서 보안 검사를 제거 하 고 그 자리에 메서드 수준의 보안을 사용 하 여 확인 하지 않는 한이 규칙 위반을 고정할 수 없습니다. 이 방식으로 위반을 수정 하는 값 형식의 인스턴스를 얻는 부적절 한 권한 있는 호출자 방지 하지 않습니다. 해당 기본 상태인 값 형식의 인스턴스는 중요 한 정보를 노출 하지 않습니다 하 고 유해한 방식으로 사용할 수 없습니다 확인 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

모든 호출자에 게 보안에 위협을 없이 해당 기본 상태인 값 형식의 인스턴스를 얻을 수 있는 경우이 규칙에서 경고를 무시할 수 있습니다.

## <a name="example-1"></a>예제 1

다음 예제에서는이 규칙을 위반 하는 값 형식을 포함 하는 라이브러리를 보여 줍니다. `StructureManager` 형식 값 형식의 인스턴스를 전달 하는 호출자가 만들거나 인스턴스에 액세스 권한이 있는지를 가정 합니다.

[!code-csharp[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]

## <a name="example-2"></a>예제 2

다음 응용 프로그램 라이브러리의 약점을 보여 줍니다.

[!code-csharp[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]

이 예제는 다음과 같은 출력을 생성합니다.

```txt
Structure custom constructor: Request failed.
New values SecuredTypeStructure 100 100
New values SecuredTypeStructure 200 200
```

## <a name="see-also"></a>참고자료

- [링크 요청](/dotnet/framework/misc/link-demands)
- [데이터 및 모델링](/dotnet/framework/data/index)
