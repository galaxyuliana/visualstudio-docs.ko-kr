---
title: 'CA1903: 대상 프레임워크의 API만 사용하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseOnlyAPIFromTargetedFramework
- CA1903
helpviewer_keywords:
- UseOnlyApiFromTargetedFramework
- CA1903
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d972198898dd1a4cafa5280c129db38bb3e4982
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921295"
---
# <a name="ca1903-use-only-api-from-targeted-framework"></a>CA1903: 대상 프레임워크의 API만 사용하세요.

|||
|-|-|
|TypeName|UseOnlyApiFromTargetedFramework|
|CheckId|CA1903|
|범주|Microsoft 이식성|
|변경 수준|중단-외부에 표시 되는 멤버 또는 형식의 서명에 대해 발생 하는 경우<br /><br /> 메서드 본문에서 발생 하는 경우에는 중단 되지 않습니다.|

## <a name="cause"></a>원인
멤버 또는 형식이 프로젝트의 대상 프레임 워크에 포함 되지 않은 Service Pack에 도입 된 멤버 또는 형식을 사용 하 고 있습니다.

## <a name="rule-description"></a>규칙 설명
새 구성원 및 형식은 .NET Framework 2.0 서비스 팩 1 및 2, .NET Framework 3.0 서비스 팩 1 및 2 및 .NET Framework 3.5 서비스 팩 1에 포함 되어 있습니다. .NET Framework의 주 버전을 대상으로 하는 프로젝트는 이러한 새 Api에 대 한 종속성을 가져올 수 있습니다. 이러한 종속성을 방지 하기 위해이 규칙은 기본적으로 프로젝트의 대상 프레임 워크에 포함 되지 않은 새 멤버와 형식을 사용 하 여 발생 합니다.

**대상 프레임 워크 및 서비스 팩 종속성**

|||
|-|-|
|대상 프레임 워크가 인 경우|에 도입 된 멤버를 사용 하 여 발생 합니다.|
|.NET Framework 2.0|.NET Framework 2.0 SP1, .NET Framework 2.0 SP2|
|.NET Framework 3.0|.NET Framework 2.0 SP1, .NET Framework 2.0 SP2, .NET Framework 3.0 SP1, .NET Framework 3.0 SP2|
|.NET Framework 3.5|.NET Framework 3.5 SP1|
|.NET Framework 4|N/A|

프로젝트의 대상 프레임 워크 [를 변경 하려면 방법: .NET 버전 대상 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
Service Pack에 대 한 종속성을 제거 하려면 새 멤버나 형식의 사용을 모두 제거 합니다. 의도적인 종속성 인 경우 경고를 표시 하지 않거나이 규칙을 해제 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우
지정 된 Service Pack의 의도적인 종속성이 아닌 경우에는이 규칙에서 경고를 표시 하지 마십시오. 이 경우이 Service Pack 설치 되지 않은 시스템에서는 응용 프로그램이 실행 되지 않을 수 있습니다. 의도적인 종속성 인 경우 경고를 표시 하지 않거나이 규칙을 해제 합니다.

## <a name="example"></a>예제
다음 예제에서는 .NET 2.0 서비스 팩 1 에서만 사용할 수 있는 DateTimeOffset 형식을 사용 하는 클래스를 보여 줍니다. 이 예제를 사용 하려면 프로젝트 속성의 대상 프레임 워크 드롭다운 목록에서 .NET Framework 2.0를 선택 해야 합니다.

[!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_1.cs)]

## <a name="example"></a>예제
다음 예에서는 DateTimeOffset 형식의 사용을 DateTime 형식으로 바꿔 이전에 설명한 위반을 수정 합니다.

[!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_2.cs)]

## <a name="see-also"></a>참고자료

- [Portability Warnings](../code-quality/portability-warnings.md)
- [Framework 대상 지정 개요](../ide/visual-studio-multi-targeting-overview.md)