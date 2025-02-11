---
title: 'CA1806: 메서드 결과를 무시하지 마세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
author: gewarren
ms.author: gewarren
dev_langs:
- CPP
- CSharp
- VB
manager: jillfra
ms.openlocfilehash: 2e68fb6b4c40c165a09ae2631a2ad0a64bf52fbc
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921551"
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: 메서드 결과를 무시하지 마세요.

|||
|-|-|
|TypeName|DoNotIgnoreMethodResults|
|CheckId|CA1806|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

이 경고는 다음과 같은 몇 가지 이유로 발생할 수 있습니다.

- 새 개체가 만들어졌지만 사용 되지 않습니다.

- 새 문자열을 만들어 반환 하는 메서드가 호출 되 고 새 문자열은 사용 되지 않습니다.

- 사용 되지 않는 HRESULT 또는 오류 코드를 반환 하는 COM 또는 P/Invoke 메서드입니다. 규칙 설명

불필요 한 개체를 만들고 사용 하지 않는 개체의 연결 된 가비지 수집을 사용 하면 성능이 저하 됩니다.

문자열은 변경할 수 없으며 ToUpper와 같은 메서드는 호출 하는 메서드에서 문자열의 인스턴스를 수정 하는 대신 문자열의 새 인스턴스를 반환 합니다.

HRESULT 또는 오류 코드를 무시 하면 오류 조건 또는 리소스 부족 상태에서 예기치 않은 동작이 발생할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
메서드 A가 사용 되지 않는 B 개체의 새 인스턴스를 만드는 경우 인스턴스를 다른 메서드에 인수로 전달 하거나 인스턴스를 변수에 할당 합니다. 개체를 만들 필요가 없으면 제거 하십시오.-또는-

메서드 A가 메서드 B를 호출 하지만 메서드 B가 반환 하는 새 문자열 인스턴스를 사용 하지 않는 경우 인스턴스를 다른 메서드에 인수로 전달 하 고, 인스턴스를 변수에 할당 합니다. 필요 하지 않은 경우 호출을 제거 합니다.

 또는

메서드 A가 메서드 B를 호출 하지만 메서드가 반환 하는 HRESULT 또는 오류 코드를 사용 하지 않는 경우 조건문에서 결과를 사용 하 고 결과를 변수에 할당 하거나 다른 메서드에 인수로 전달 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
개체를 만드는 작업을 수행 하는 경우를 제외 하 고는이 규칙에서 경고를 표시 하지 마십시오.

## <a name="example"></a>예제
다음 예제에서는 호출 된 String.format의 결과를 무시 하는 클래스를 보여 줍니다.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
[!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]

## <a name="example"></a>예제
다음 예에서는 문자열의 결과를 할당 하 여 이전 위반을 수정 합니다 .를 호출한 변수로 다시 트리밍합니다.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
[!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]

## <a name="example"></a>예제
다음 예제에서는 만든 개체를 사용 하지 않는 메서드를 보여 줍니다.

> [!NOTE]
> Visual Basic에서이 위반을 재현할 수 없습니다.

[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]

## <a name="example"></a>예제
다음 예제에서는 불필요 한 개체 생성을 제거 하 여 이전 위반을 수정 합니다.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)]

<!-- Examples don't exist for the below... -->
<!--
## Example
The following example shows a method that ignores the error code that the native method GetShortPathName returns.

## Example
The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.
-->