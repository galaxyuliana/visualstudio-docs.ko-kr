---
title: 'CA1050: 네임스페이스에 형식을 선언하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 869ff99243349ae01c63da0a7d9e6544761cbd39
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922507"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: 네임스페이스에 형식을 선언하세요.

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
Public 또는 protected 형식은 명명 된 네임 스페이스의 범위 밖에 서 정의 됩니다.

## <a name="rule-description"></a>규칙 설명
형식은 이름 충돌을 방지 하기 위해 네임 스페이스에 선언 되며, 개체 계층 구조에서 관련 형식을 구성 하는 방법으로 선언 됩니다. 명명 된 네임 스페이스 외부에 있는 형식은 코드에서 참조할 수 없는 전역 네임 스페이스에 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
이 규칙 위반 문제를 해결 하려면 형식을 네임 스페이스에 저장 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
이 규칙에서는 경고를 표시 하지 않아도 되지만 어셈블리를 다른 어셈블리와 함께 사용 하지 않을 경우에는이 작업을 수행 하는 것이 안전 합니다.

## <a name="example"></a>예제
다음 예제에서는 네임 스페이스 외부에 잘못 선언 된 형식 및 네임 스페이스에 선언 된 동일한 이름의 형식을 가진 라이브러리를 보여 줍니다.

[!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
[!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>예제
다음 응용 프로그램은 이전에 정의 된 라이브러리를 사용 합니다. 네임 스페이스에 의해 정규화 되지 않은 이름 `Test` 으로 네임 스페이스 외부에서 선언 된 형식이 만들어집니다. 또한의 `Test` `Goodspace`형식에 액세스 하려면 네임 스페이스 이름이 필요 합니다.

[!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
[!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]