---
title: 'CA1030: 적절한 경우 이벤트를 사용하세요.'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ad0659241e75c862b3d82c64a7e8b2ad3ccada21
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547671"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: 적절한 경우 이벤트를 사용하세요.

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|범주|Microsoft.Design|
|변경 수준|최신이 아님|

## <a name="cause"></a>원인

메서드 이름은 다음 중 하나로 시작 됩니다.

- AddOn
- RemoveOn
- 시키고
- 올리려면

기본적으로이 규칙은 외부에서 볼 수 있는 메서드만 볼 수 있지만이는 [구성 가능](#configurability)합니다.

## <a name="rule-description"></a>규칙 설명

이 규칙에서는 보통 이벤트에 사용되는 이름을 갖는 메서드를 찾아냅니다. 이벤트는 관찰자 또는 게시-구독 디자인 패턴을 따릅니다. 한 개체의 상태 변경 내용을 다른 개체와 통신 해야 하는 경우에 사용 됩니다. 명확 하 게 정의 된 상태 변경에 대 한 응답으로 메서드를 호출 하는 경우에는 이벤트 처리기에서 메서드를 호출 해야 합니다. 메서드를 호출하는 개체는 메서드를 직접 호출하는 대신 이벤트를 발생시켜야 합니다.

사용자 인터페이스 응용 프로그램에서 단추를 클릭 하 여 코드 세그먼트를 실행 하는 것과 같은 사용자 작업을 수행 하는 몇 가지 일반적인 이벤트 예제가 있습니다. .NET 이벤트 모델은 사용자 인터페이스로 제한 되지 않습니다. 하나 이상의 개체에 상태 변경 내용을 전달 해야 하는 모든 곳에서 사용 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

개체의 상태가 변경 될 때 메서드가 호출 되 면 .NET 이벤트 모델을 사용 하도록 디자인을 변경 하는 것이 좋습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하지 않는 경우

메서드가 .NET 이벤트 모델에서 작동 하지 않는 경우이 규칙에서 경고를 표시 하지 않습니다.

## <a name="configurability"></a>구성이

레거시 분석이 아닌 [FxCop 분석기](install-fxcop-analyzers.md) 에서이 규칙을 실행 하는 경우 해당 액세스 가능성에 따라이 규칙을 실행할 코드 베이스 부분을 구성할 수 있습니다. 예를 들어 public이 아닌 API 화면에 대해서만 규칙을 실행 하도록 지정 하려면 프로젝트의 editorconfig 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.ca1030.api_surface = private, internal
```

이 규칙에 대해서만이 옵션을 구성 하거나, 모든 규칙에 대해 또는이 범주의 모든 규칙에 대해이 옵션을 구성할 수 있습니다 (디자인). 자세한 내용은 [FxCop 분석기 구성](configure-fxcop-analyzers.md)을 참조 하세요.
