---
title: 이 관련 메서드는 다음과 같은 기본 삽입, 업데이트 및 삭제 메서드를 지원하는 메서드입니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 4b478f041dcd94cff58f9bff8121e8d6e3b8acd3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069345"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>이 관련 메서드는 다음과 같은 기본 삽입, 업데이트 및 삭제 메서드를 지원하는 메서드입니다.

이 관련 메서드는 다음과 같은 기본을 지 원하는 메서드입니다 `Insert`하십시오 `Update`, 또는 `Delete` 메서드. 이 관련 메서드를 삭제하면 이러한 메서드도 삭제됩니다. 계속하시겠습니까?

선택한 `DataContext` 메서드 중 하나로 현재 사용 되는 `Insert`를 `Update`, 또는 `Delete` 엔터티 클래스 중 하나에 대 한 메서드를 **O/R 디자이너**합니다. 삭제는 선택한 메서드를 사용 하면 삽입을 수행 하기 위한 기본 런타임 동작으로 되돌리려면이 메서드를 사용 하 던 엔터티 클래스 업데이트 또는 업데이트 하는 동안 삭제 합니다.

## <a name="selected-method-options"></a>선택한 방법 옵션

- 런타임 업데이트를 사용 하도록 엔터티 클래스를 선택한 메서드를 삭제 하려면 클릭 **예**합니다.

   선택한 메서드가 삭제되고 업데이트 동작을 재정의하기 위해 이 메서드를 사용하는 모든 클래스가 기본 LINQ to SQL 런타임 동작을 사용하도록 되돌립니다.

- 선택한 메서드를 변경 하지 않고 메시지 상자를 닫으려면 **No**합니다.

   메시지 상자가 닫히고 변경되지 않습니다.

## <a name="see-also"></a>참고 항목

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)