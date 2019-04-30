---
title: 'CA2106: 어설션을 안전하게 보호하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8d80c4e9a21c29ce7b34a3998e241b11713f355
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545702"
---
# <a name="ca2106-secure-asserts"></a>CA2106: 어설션을 안전하게 보호하세요.

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 메서드 사용 권한을 어설션 하 고 호출자의 보안 검사를 수행 합니다.

## <a name="rule-description"></a>규칙 설명
 보안 검사를 수행하지 않고 보안 권한을 어설션하면 코드에 보안상 취약한 부분이 남아 있을 수 있습니다. 보안 스택 워크는 보안 권한이 어설션 되 면 중지 합니다. 사용 권한을 호출자에 대 한 검사를 수행 하지 않고에 어설션하 면 호출자에 게 직접 코드를 실행할 수 없습니다 권한을 사용 하 여 합니다. 보안 검사 assert 유해한 방식으로 사용할 수 없습니다 경우에 허용 하지 않고 어설션 합니다. Assert는 치명적이 지 호출 하는 코드는 치명적이 지, 아니면 사용자가 호출 하는 코드를 임의의 정보를 전달할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드 또는 해당 선언 형식에는 보안 요청을 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 신중 하 게 보안을 검토 한 후에이 규칙에서 경고를 표시 합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)