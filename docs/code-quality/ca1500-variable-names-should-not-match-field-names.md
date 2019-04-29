---
title: 'CA1500: 변수 이름은 필드 이름과 달라야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 740edb9861d2e3e758a36dfc067cb85fe4fc2c7e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807162"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: 변수 이름은 필드 이름과 달라야 합니다.

|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|범주|Microsoft.Maintainability|
|변경 수준|필드 이름이 같은 매개 변수에 대해와 발생 합니다.<br /><br /> --아님-필드와 메서드 매개 변수를 선언 하는 어셈블리 외부에서 변경 내용이 관계 없이 볼 수 없는 경우.<br />줄 바꿈하지-필드의 이름을 변경 하 고 어셈블리 외부에서 볼 수 있습니다.<br />-주요-매개 변수의 이름을 변경 하 고 어셈블리 외부에서 선언 하는 메서드를 볼 수 있습니다.<br /><br /> 필드와 동일한 이름을 가진 로컬 변수로에서 발생 합니다 한 경우:<br /><br /> --아님-어셈블리 외부에서 변경 내용이 관계 없이 필드를 볼 수 없는 경우.<br />--아님-로컬 변수의 이름을 변경 하 고 필드의 이름을 변경 하지 마세요.<br />-주요-필드의 이름을 변경 하 고 어셈블리 외부에서 볼 수 있습니다.|

## <a name="cause"></a>원인

인스턴스 메서드는 매개 변수 또는 이름이 선언 형식의 인스턴스 필드와 지역 변수를 선언 합니다. 규칙을 위반 하는 지역 변수를 catch 하려면 테스트 되는 어셈블리 디버깅 정보를 사용 하 여 작성 해야 하 고 연결된 프로그램 데이터베이스 (.pdb) 파일을 사용할 수 있어야 합니다.

## <a name="rule-description"></a>규칙 설명

인스턴스 필드의 이름을 매개 변수 또는 지역 변수 이름과 일치 하는 경우 인스턴스 필드를 사용 하 여 액세스 합니다 `this` (`Me` 에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 메서드 본문 내에 있을 때 키워드입니다. 코드를 유지 관리할 때 오류가 발생 하는 인스턴스 필드 매개 변수/로컬 변수 참조는 가정 하는 것이 차이점을 잊지 쉽습니다. 시간이 오래 걸리는 메서드 본문에 특히 그렇습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 매개 변수/변수 또는 필드를 이름을 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 두 가지 규칙 위반을 보여 줍니다.

[!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
[!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]