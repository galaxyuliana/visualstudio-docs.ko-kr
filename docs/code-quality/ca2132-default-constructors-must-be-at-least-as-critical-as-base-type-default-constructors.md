---
title: 'CA2132: 기본 생성자는 기본 형식의 기본 생성자 이상으로 중요해야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cfe6e4f3ce896e5ae3d728a002bf2caf9f1948ef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013537"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: 기본 생성자는 기본 형식의 기본 생성자 이상으로 중요해야 합니다.

|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

> [!NOTE]
> 이 경고는 CoreCLR (Silverlight 웹 응용 프로그램에 관련 된 CLR의 버전)를 실행 하는 코드에만 적용 됩니다.

## <a name="cause"></a>원인

파생된 클래스의 기본 생성자의 투명성 특성이 기본 클래스의 투명도를으로 중요 하지 않습니다.

## <a name="rule-description"></a>규칙 설명

형식 및 멤버를는 <xref:System.Security.SecurityCriticalAttribute> Silverlight 응용 프로그램 코드에서 사용할 수 없습니다. 보안에 중요한 형식 및 멤버는 .NET Framework for Silverlight 클래스 라이브러리의 신뢰할 수 있는 코드에서만 사용할 수 있습니다. 파생 클래스의 public 또는 protected 구성 요소는 투명성이 기본 클래스보다 높거나 같아야 하기 때문에 애플리케이션의 클래스는 SecurityCritical로 표시된 클래스에서 파생될 수 없습니다.

CoreCLR 플랫폼 코드에 대 한 기본 형식에 public 또는 protected 불투명 기본 생성자가 하는 경우 다음 파생된 형식을 준수 해야 기본 생성자 상속 규칙입니다. 파생된 형식에 기본 생성자가 있어야 하 고 해당 생성자는 기본 형식의 중요 한 기본 생성자로 이상 이어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

위반을 해결 하려면 유형을 제거 하거나 보안 투명이 아닌 형식에서 파생 되지 않은 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 표시 하지 마십시오. 응용 프로그램 코드에서이 규칙이 위반 하면 거부 인 형식을 로드할 CoreCLR을 <xref:System.TypeLoadException>입니다.

### <a name="code"></a>코드

[!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors_1.cs)]