---
title: 'CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4557b61afab08c7db05c734c6f2ac927a40edb71
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546857"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.

|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

형식이 같음 연산자 또는 같지 않음 연산자를 구현하면서 그 반대 연산자를 구현하지 않습니다.

기본적으로이 규칙은 외부에서 볼 수 있는 형식만 볼 수 있지만이를 [구성할](#configurability)수 있습니다.

## <a name="rule-description"></a>규칙 설명

같음 또는 같지 않음이 형식의 인스턴스에 적용 되 고 반대쪽 연산자는 정의 되지 않은 상황이 발생 하지 않습니다. 형식은 일반적으로 같음 연산자의 부정 값을 반환 하 여 같지 않음 연산자를 구현 합니다.

C# 컴파일러가이 규칙 위반에 대해 오류를 발생 시킵니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 같음 연산자와 같지 않음 연산자를 모두 구현 하거나 존재 하는 연산자를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

이 규칙에서는 경고를 표시해야 합니다. 이렇게 하면 형식이 .NET과 일치 하는 방식으로 작동 하지 않습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca2226.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (사용량). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.

## <a name="related-rules"></a>관련 규칙

- [CA1046: 참조 형식에 같음 연산자를 오버 로드 하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225: 연산자 오버 로드에는 대체 이름이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2224: 오버 로드 연산자 equals에 대 한 Override equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Equals를 재정의할 때 GetHashCode 재정의](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)